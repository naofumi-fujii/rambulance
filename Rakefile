# encoding: utf-8
require "bundler/gem_tasks"
require "rspec/core"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

task default: "spec:all"

namespace :spec do
  desc "Run Tests with the default exceptions app"
  task :default do
    sh "bundle exec rake -t spec"
  end

  desc "Run Tests with a custom exceptions app"
  task :custom do
    sh "CUSTOM_EXCEPTIONS_APP=1 bundle exec rake -t spec"
  end

  desc "Run tests with both of the default and custom apps"
  task(:all).enhance(%w(default custom))
end
