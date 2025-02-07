require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "socialcast-opengraph"
    gem.summary = %Q{A very simple Ruby library for parsing Open Graph prototocol information from websites.}
    gem.description = %Q{A very simple Ruby library for parsing Open Graph prototocol information from websites. See http://opengraphprotocol.org for more information.}
    gem.email = "michael@intridea.com"
    gem.homepage = "http://github.com/intridea/opengraph"
    gem.authors = ["Michael Bleigh"]
    gem.add_dependency 'hashie'
    gem.add_dependency 'nokogiri', '~> 1.5.0'
    gem.add_dependency 'rest-client', '~> 1.6.0'
    gem.add_development_dependency "rspec", ">= 1.2.9"
    gem.add_development_dependency 'webmock'
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "opengraph #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
