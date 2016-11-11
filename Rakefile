# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require_relative 'config/application'

Rails.application.load_tasks

require 'solr_wrapper/rake_task' unless Rails.env.production?

unless Rails.env == 'production'
  require 'rubocop/rake_task'

  desc 'Run style checker'
  RuboCop::RakeTask.new(:rubocop) do |task|
    task.fail_on_error = true
  end
end
