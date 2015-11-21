# Variables:
#
# SIMP_GEM_SERVERS | a space/comma delimited list of rubygem servers
# PUPPET_VERSION   | specifies the version of the puppet gem to load
puppetversion = ENV.key?('PUPPET_VERSION') ? "#{ENV['PUPPET_VERSION']}" : '~>3'
gem_sources   = ENV.key?('SIMP_GEM_SERVERS') ? ENV['SIMP_GEM_SERVERS'].split(/[, ]+/) : ['https://rubygems.org']

gem_sources.each { |gem_source| source gem_source }

group :test do
  gem "rake"
  gem 'puppet', puppetversion
  gem "rspec", '< 3.2.0'
  gem "rspec-puppet"
  gem "puppetlabs_spec_helper"
  gem "metadata-json-lint"
  gem "simp-rspec-puppet-facts"

  gem 'modulesync'
  # # dependency hacks:
  # gem "fog-google", '~> 0.0.9' # 0.1 dropped support for ruby 1.9

  # # simp-rake-helpers does not suport puppet 2.7.X
  # if "#{ENV['PUPPET_VERSION']}".scan(/\d+/).first != '2' &&
  #     # simp-rake-helpers and ruby 1.8.7 bomb Travis tests
  #     # TODO: fix upstream deps (parallel in simp-rake-helpers)
  #     RUBY_VERSION.sub(/\.\d+$/,'') != '1.8'
  #   gem 'simp-rake-helpers'
  # end
end
