require 'rubygems'
require 'bundler'
Bundler.setup(:default, :development)

require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  gem.name = "moses-rspec-spies"
  gem.summary = %Q{rspec has gone without test spies. no more!}
  gem.version = File.exist?('VERSION') ? File.read('VERSION') : ""
  gem.description = %Q{test spies, for rspec (forked from technicalpickles/rspec-spies)}
  gem.email = "moses@moseshohman.com"
  gem.homepage = "http://github.com/moses/rspec-spies"
  gem.authors = ["Joshua Nichols", "Moses Hohman"]
  # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
end
Jeweler::GemcutterTasks.new

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new do |t|
  t.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |t|
  t.pattern = FileList['spec/**/*_spec.rb']
  t.rcov = true
  t.rcov_opts = ['--exclude', 'spec']
end

task :default => :spec

require 'rdoc/task'
RDoc::Task.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "rspec-spies #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
