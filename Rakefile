# frozen_string_literal: true

require 'bundler/gem_tasks'

require 'rake/testtask'
require 'rspec/core/rake_task'

begin
  require 'rubocop/rake_task'
rescue LoadError
  puts 'can not use rubocop in this environment'
else
  RuboCop::RakeTask.new
end

task default: [:test_behaviors]
task test_behaviors: [:test, :spec]

multitask simulate_ci: [:test_behaviors, :validate_signatures, :rubocop]

Rake::TestTask.new(:test) do |tt|
  tt.pattern = 'test/**/test_*.rb'
  tt.verbose = true
  tt.warning = true
end

RSpec::Core::RakeTask.new(:spec) do |rt|
  rt.ruby_opts = %w[-w]
end

task validate_signatures: [:test_yard, :'signature:validate']

namespace :signature do
  task :validate do
    sh 'bundle exec rbs -rsecurerandom -rmonitor -I sig validate'
  end

  task :check_false_positive do
    sh 'bundle exec steep check --log-level=fatal'
  end
end

task :test_yard do
  sh "bundle exec yard --fail-on-warning #{'--no-progress' if ENV['CI']}"
end

task :yard do
  sh 'bundle exec yard --fail-on-warning'
end

task :benchmark do
  sh 'bundle exec ruby ./benchmark/example.rb'
end
