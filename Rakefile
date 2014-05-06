require 'rake/testtask'

# To get started testing, run `crowd -c test/config load_schema`, in order to
# create and load a fresh test database, and then `rake test`.
desc 'Run all tests'
task :test do
  require 'minitest/autorun'
  $LOAD_PATH.unshift(File.expand_path('test'))
  Dir['./test/**/test_*.rb'].each {|test| require test }
end

namespace :gem do
  
  desc 'Build and install cloud-crowd gem'
  task :install do
    sh "gem build cloud-crowd.gemspec"
    sh "sudo gem install #{Dir['*.gem'].join(' ')} --local --no-ri --no-rdoc"
  end
  
  desc 'Uninstall the cloud-crowd gem'
  task :uninstall do
    sh "sudo gem uninstall -x cloud-crowd"
  end
  
end

task :default => :test
