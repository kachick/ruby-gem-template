# coding: us-ascii
# frozen_string_literal: true

source('https://rubygems.org')

gemspec

group(:development, :test) do
  gem('rake', '~> 13.2.1')
  gem('irb', '~> 1.13.0')
  gem('irb-power_assert', '~> 0.2.0')
end

group(:development) do
  gem('debug', '~> 1.9.2', require: false)
  gem('benchmark-ips', '~> 2.13.0', require: false)
  gem('rubocop', '~> 1.63.4', require: false)
  gem('rubocop-rake', '~> 0.6.0', require: false)
  gem('rubocop-performance', '~> 1.21.0', require: false)
  gem('rubocop-thread_safety', '~> 0.5.1', require: false)
end

group(:test) do
  gem('test-unit', '~> 3.6.2')
  gem('rspec', '~> 3.13.0')
  gem('rspec-matchers-power_assert_matchers', '~> 0.2.0')
  gem('warning', '~> 1.3.0')
end
