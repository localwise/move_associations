require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "move_associations"
    gem.summary = %Q{A gem for ActiveRecord to move associated records based on has_many and has_one associations. }
    gem.description = %Q{This gem extends ActiveRecord to move associated records based on has_many and has_one associations. }
    gem.email = "alex@mosterlabs.com.mx"
    gem.homepage = "http://github.com/monsterlabs/move_associations"
    gem.authors = ["Alejandro Juarez"]
    gem.add_development_dependency "shoulda"
    gem.add_dependency "activerecord", "~> 3.0.0"
    gem.add_dependency "activesupport", "~> 3.0.0"
    gem.files =  FileList["[A-Z]*", "{lib}/**/*"]
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "move_associations #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
