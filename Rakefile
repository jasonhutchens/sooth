# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://guides.rubygems.org/specification-reference/ for more options
  gem.name = "sooth"
  gem.homepage = "http://github.com/jasonhutchens/sooth"
  gem.license = "MIT"
  gem.summary = %Q{A small thing for generating codes for users to type into places}
  gem.description = %Q{Does what it says on the box}
  gem.email = "jasonhutchens@gmail.com"
  gem.authors = ["Jason Hutchens"]
  gem.required_ruby_version = "~> 2.1"
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/extensiontask'
Rake::ExtensionTask.new('sooth_native')

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

desc "Code coverage detail"
task :simplecov do
  ENV['COVERAGE'] = "true"
  Rake::Task['spec'].execute
end

task :default => :spec

require 'yard'
YARD::Rake::YardocTask.new