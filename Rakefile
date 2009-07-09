require 'spec/rake/spectask'
require 'detexify'
require 'storage'

task :default => [:spec]

Spec::Rake::SpecTask.new do |t|
  t.warning = true
  t.rcov = true
end

desc "create images from symbols.yaml"
task :create do
   Latex::Storage::create_all
   Latex::Storage::index
end

namespace :features do

  desc "regenerate all feature vectors"
  task :regenerate do
    c = Detexify::Classifier.new
    c.regenerate_features
  end
  
end