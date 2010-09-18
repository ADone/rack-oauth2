require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = 'rack-oauth2'
    gem.summary = %Q{Rack Middleware for OAuth2 Server}
    gem.description = %Q{Rack Middleware for OAuth2. Currently support only Server/Provider, not Client/Consumer.}
    gem.email = 'nov@matake.jp'
    gem.homepage = 'http://github.com/nov/rack-oauth2'
    gem.authors = ['nov matake']
    gem.add_dependency 'json'
    gem.add_dependency 'activesupport'
    gem.add_development_dependency 'rspec', '>= 1.2.9'
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts 'Jeweler (or a dependency) not available. Install it with: gem install jeweler'
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
  spec.rcov_opts = ['--exclude spec,gems']
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ''

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = 'rack-oauth2 #{version}'
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
