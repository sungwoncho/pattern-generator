# Pattern Generator [![Build Status](https://travis-ci.org/sungwoncho/pattern_generator.svg?branch=master)](https://travis-ci.org/sungwoncho/pattern_generator)

Pattern Generator lets you generate various Rails patterns and tests with a single
command.


## Install

In your Gemfile, add the gem in the development group.

```ruby
gem 'pattern_generator', group: :development
```

Run `bundle install` to install the gem.

Now you are ready to rock the pattern generator!


## Usage

```
rails generate [PATTERN_TYPE] [YOUR_FILE_NAME (in snake_case)]
```

Currently, PATTERN_TYPE can be:

* Service
* Policy

Destroy command is also supported.


## Examples

Here are usage examples with commands and generated files.

### Service

```
rails generate service find_match
```

generates:


*app/services/find_match_service.rb*
```ruby
class FindMatchService
  def initialize

  end

  def call

  end
end
```

*spec/services/find_match_service_spec.rb*
```ruby
require 'rails_helper'

RSpec.describe FindMatchService, type: :service do
  describe '#call' do
    it 'performs something' do

    end
  end
end
```

### Policy

```
rails generate policy voting
```

generates:


*app/policies/voting_policy.rb*
```ruby
class VotingPolicy
  def initialize

  end

  def policy_method
    # Customize to fit your need
  end
end
```

*spec/policies/voting_policy_spec.rb*
```ruby
require 'rails_helper'

RSpec.describe VotingPolicy, type: :policy do
  describe '#policy_method' do
    it 'does something' do

    end
  end
end
```


## Options

* `--test-suite`

  * Specify the test suite to generate the test files with. (`minitest` or `rspec`).
  * DEFAULT: `rspec`
  * Usage: `rails generate service subscribe_user --test-suite=minitest`


## Contributing

Know your patterns? Open a pull request!

This project respects the [contributor code of conduct](https://github.com/sungwoncho/pattern_generator/blob/master/code_of_conduct.md).

## License

This project rocks and uses MIT-LICENSE.
