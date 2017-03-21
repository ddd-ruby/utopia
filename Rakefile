require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:test)

task :documentation do
	sh('yard', '-o', "documentation/public/code")
	
	ENV.delete 'BUNDLE_BIN_PATH'
	ENV.delete 'BUNDLE_GEMFILE'
	
	Dir.chdir('documentation') do
		sh('bundle', 'install', '--quiet')
		sh('bundle', 'exec', 'rake')
	end
end

task :default => :documentation
