require "rake/testtask"
require "bundler/gem_tasks"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the `hello` task."
end
## if we didnt have testtask, we could do this:

# desc 'Run tests'
# task :test do
#   sh 'ruby ./test/todolist_project_test.rb' ## `sh` is like `$ruby`
# end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Display inventroy of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.')
    return name if File.file?(name)
  end
end