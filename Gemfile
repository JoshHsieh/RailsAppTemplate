require 'yaml'
env = ENV["RAILS_ENV"] || 'development'
dbfile = File.expand_path("../config/database.yml", __FILE__)

unless File.exists?(dbfile)
  raise "You need to configure config/database.yml first"
else
  conf = YAML.load(File.read(dbfile))
  environment = conf[env]
  adapter = environment['adapter'] if environment
  raise "You need define an adapter in your database.yml or set your RAILS_ENV variable" if adapter == '' || adapter.nil?
  case adapter
  when 'sqlite3'
    gem 'sqlite3'
  when 'postgresql'
    gem 'pg', '~> 0.14.1'
  when 'mysql2'
    gem 'mysql2'
  else
    raise "Don't know what gem to use for adapter #{adapter}"
  end
end

source 'http://rubygems.org'

gem 'rails', '~> 3.2.13'

# Bundle edge Rails instead:
# gem 'rails', :git => 'git://github.com/rails/rails.git'

# gem 'mysql2'
# gem 'sqlite3-ruby', :require => 'sqlite3'
# gem 'moneta'

gem 'yajl-ruby', :require => 'yajl'
gem 'nokogiri'

# Paginator
# gem "kaminari"
# gem 'will_paginate', '3.0.pre2'

# File Uploads
# gem 'paperclip'
# gem 'carrierwave'

# gem 'devise', '~> 1.1.7'
# gem "cancan"
# gem "simple_form"
# gem 'fastercsv' # for Ruby 1.8.7+
# gem 'prawn'
# gem "haml"
# gem "haml-rails"
# gem 'validates_timeliness', '~> 3.0.5'
# gem 'acts-as-taggable-on'

# gem 'hoptoad_notifier'
# gem 'newrelic_rpm'

gem 'SystemTimer' if RUBY_VERSION =~ /^1.8/

group :test, :development do
  gem "rspec", "~> 2.0"
  gem "rspec-rails", "~> 2.0"
  gem "factory_girl_rails"
  gem "shoulda-matchers"
  gem "rcov"
  gem "delorean"
  gem "watchr"
  # gem "capybara"
  # gem 'yard'
  # gem "bluecloth"
end

# State machine
# gem 'aasm'
# gem 'state_machine'

# HTTP client
# gem 'typhoeus'
# gem 'rest-client', :require => 'restclient'

# Memcached client
# gem "dalli"
# gem "memcache-client", :require => "memcache"

# Deployment tool
# gem 'capistrano'
# gem 'whiskey_disk'

# Debugger (ruby-debug for Ruby 1.8.7+, ruby-debug19 for Ruby 1.9.2+)
# gem 'ruby-debug'
# gem 'ruby-debug19'

# Background Processing
# gem 'delayed_job'
# gem 'resque'

# Full-text search engine
# gem 'thinking-sphinx', '~> 2.0.2', :require => 'thinking_sphinx'
