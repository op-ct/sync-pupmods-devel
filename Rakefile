require 'rake/clean'
require 'rubocop/rake_task'

RuboCop::RakeTask.new

CLEAN   << 'modules'
CLOBBER << 'modules'

desc <<-EOM
        Download everything into `modules/` & whack in common assets.
            * :jira_issue - The Jira Issue (e.g., "SIMP-###") for this update.
        EOM
task :suck, [:jira_issue] => [:clean] do |_, args|
  raise 'The JIRA issue (e.g., "SIMP-###") is required!' unless args.jira_issue
  sh "msync update --noop --branch #{args[:jira_issue]}"
end
