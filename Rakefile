require "bundler/gem_tasks"
require 'rake/testtask'
require 'find'

desc 'Say Hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run Tests'
task :default => :test

Rake::TestTask.new(:test) do |t|  # allows you to add any # of new test files
  t.libs << "test"  # tells rake where source code files reside
  t.libs << "lib"   # specify folder name
  t.test_files = FileList['test/**/*_test.rb'] # in test dir, end with _test.rb
end

desc "List All Files in Project (except hidden dir's & files)"
task :inventory do
  Find.find(".") do |name|
    next if name.include?("/.") # exclude files & directories w/ . names
    puts name if File.file?(name)
  end
end

