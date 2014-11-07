require 'rspec/core/rake_task'

task(:spec).clear
namespace :spec do
  RSpec::Core::RakeTask.new(:all) do |t|
    t.rspec_opts = '--color --format=documentation'
    t.pattern = 'spec/**/*_spec.rb'
  end

  RSpec::Core::RakeTask.new(:integration) do |t|
    t.rspec_opts = '--color --format=documentation'
    t.pattern = 'spec/features/**/*_spec.rb'
  end

  RSpec::Core::RakeTask.new(:unit) do |t|
    t.pattern = Dir.glob('spec/**/*_spec.rb').reject { |f| f.include?('features/') }
    t.rspec_opts = '--color --format=documentation'
  end
end

task spec: ['spec:all']
task default: ['spec']
