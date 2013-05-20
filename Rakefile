require 'foodcritic'

require 'emeril/rake_tasks'

Emeril::RakeTasks.new do |t|
  t.config[:logger].level = :debug
end

FoodCritic::Rake::LintTask.new do |t|
  t.options = { :fail_tags => ['any'] }
end

begin
  require 'kitchen/rake_tasks'
  Kitchen::RakeTasks.new
rescue LoadError
  puts ">>>>> Kitchen gem not loaded, omitting tasks" unless ENV['CI']
end
