require 'rubygems'
require 'rake'
require 'spec/rake/spectask'

require File.join(File.dirname(__FILE__), 'lib', 'plastic', 'version')

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "plastic"
    gem.summary = "Credit card library for Ruby."
    gem.description = "Handle credit, debit, bank and other cards."
    gem.email = "github@squareup.com"
    gem.homepage = "http://github.com/square/plastic"
    gem.authors = ["Randy Reddig", "Cameron Walters", "Matthew O'Connor", "Damon McCormick"]
    gem.version = Plastic::VERSION::STRING
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

desc "Run all specs"
Spec::Rake::SpecTask.new do |t|
  t.spec_opts = ["--options", "spec/spec.opts"]
  t.spec_files = FileList["spec/**/*_spec.rb"]
  t.rcov = ENV["RCOV"]
  t.rcov_opts = %w{--exclude osx\/objc,gems\/,spec\/}
  t.verbose = true
end

task :spec => :check_dependencies
task :default => :spec
