# coding: us-ascii
# frozen_string_literal: true

source('https://rubygems.org')

gemspec

group(:development, :test) do
  gem('rake', '~> 13.0.6')
  gem('irb', '~> 1.8.1')
  gem('irb-power_assert', '~> 0.2.0')
end

group(:development) do
  gem('debug', '~> 1.8.0', require: false)
  gem('yard', '~> 0.9.34', require: false)
  gem('benchmark-ips', '~> 2.12.0', require: false)
  gem('rubocop', '~> 1.57.1', require: false)
  gem('rubocop-rake', '~> 0.6.0', require: false)
  gem('rubocop-performance', '~> 1.19.1', require: false)
  gem('rubocop-thread_safety', '~> 0.5.1', require: false)
end

group(:test) do
  gem('test-unit', '~> 3.6.1')
  gem('rspec', '~> 3.12.0')
  gem('rspec-matchers-power_assert_matchers', '~> 0.2.0')
  gem('warning', '~> 1.3.0')
end
