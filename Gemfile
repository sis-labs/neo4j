source 'http://rubygems.org'

gemspec

# gem 'neo4j-core', github: 'neo4jrb/neo4j-core', branch: 'master' if ENV['CI']

if branch = ENV['TRAVIS_BRANCH']
  same_branch_exists = `curl --head https://github.com/neo4jrb/neo4j-core/tree/#{branch} | head -1`.match(/200 OK/)
  gem 'neo4j-core', github: 'neo4jrb/neo4j-core', branch: same_branch_exists ? branch : 'master'
elsif ENV['USE_LOCAL_CORE']
  gem 'neo4j-core', path: '../neo4j-core'
else
  gem 'neo4j-core'
end

# gem 'active_attr', github: 'neo4jrb/active_attr', branch: 'performance'
# gem 'active_attr', path: '../active_attr'

gem 'listen', '< 3.1'

if RUBY_VERSION.to_f < 2.2
  gem 'activemodel', '~> 4.2'
  gem 'activesupport', '~> 4.2'
  gem 'railties', '~> 4.2'
end

group 'test' do
  gem 'coveralls', require: false
  if RUBY_VERSION.to_f < 2.0
    gem 'term-ansicolor', '< 1.4'
    gem 'tins', '< 1.7'
    gem 'overcommit', '< 0.35.0'
  else
    gem 'overcommit'
  end
  gem 'codecov', require: false
  gem 'simplecov', require: false
  gem 'simplecov-html', require: false
  gem 'rspec', '~> 3.4'
  gem 'its'
  gem 'test-unit'
  gem 'colored'
  gem 'dotenv'
  gem 'timecop'
end
