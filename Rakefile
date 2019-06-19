# frozen_string_literal: true

require 'find'
require 'rake/testtask'

desc 'Say hello'
task :hello do
  puts 'Hello there. This is the "hello" task.'
end

desc 'Run tests'
task default: :test

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List files'
task :list_files do
  puts "Files in project: #{File.basename(__dir__)}"
  Find.find(__dir__) do |path|
    name = File.basename path
    if FileTest.directory? path
      Find.prune if name.start_with? '.'
    end
    puts name unless FileTest.directory?(path) || name.start_with?('.')
  end
end
