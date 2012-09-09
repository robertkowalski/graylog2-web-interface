# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require File.expand_path('../config/application', __FILE__)
Graylog2WebInterface::Application.load_tasks


def trap_load_error
  yield
rescue LoadError
  # do nothing
end

desc "Run Phantom JS Unit tests"
task :phantomjs do
  cmd = "phantomjs test/javascript/run-qunit.js \"file://localhost#{File.dirname(__FILE__)}/test/javascript/jquery.graylog2shell.html\""
  system(cmd)
end


trap_load_error { require 'metric_fu' }
trap_load_error { require 'ci/reporter/rake/test_unit' }
