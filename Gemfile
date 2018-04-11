source 'https://rubygems.org'

gem 'rake'

platforms :ruby do
  gem 'sqlite3'
end

platforms :jruby do
  if ENV['RAILS_VERSION'] == '~> 4.2.0'
    gem 'activerecord-jdbcsqlite3-adapter', '< 50.0'
  else
    gem 'activerecord-jdbcsqlite3-adapter'
  end
  gem 'jruby-openssl'
  gem 'mime-types', ['~> 2.6', '< 2.99']
  if ENV['RAILS_VERSION'] == 'edge'
    gem 'railties', :github => 'rails/rails'
  else
    gem 'railties', (ENV['RAILS_VERSION'] || ['>= 3.0', '< 5.2'])
  end
end

platforms :rbx do
  gem 'psych'
end

group :test do
  if ENV['RAILS_VERSION'] == 'edge'
    gem 'actionmailer', :github => 'rails/rails'
    gem 'activerecord', :github => 'rails/rails'
  else
    gem 'actionmailer', (ENV['RAILS_VERSION'] || ['>= 3.0', '< 5.3'])
    gem 'activerecord', (ENV['RAILS_VERSION'] || ['>= 3.0', '< 5.3'])
  end

  gem 'coveralls', :require => false
  gem 'rspec', '>= 3'
  gem 'rubocop', '>= 0.25', '< 0.49'
  gem 'simplecov', '>= 0.9'
end

gemspec
