# Paypal::Sdk::Core

Core library for PayPal ruby SDK.

## Installation

Add this line to your application's Gemfile:

    gem 'paypal-sdk-core', :git => "https://github.com/paypal/sdk-core.git", :branch => "ruby-sdk"

And then execute:

    $ bundle
    
Run Testcase

    $ bundle exec rspec


## Usage

```ruby
# Load Configurations from file
PayPal::SDK::Core::Config.load('config/paypal.yml', 'development')

# Get Configuration
config = PayPal::SDK::Core::Config.config # Load default configuration
config = PayPal::SDK::Core::Config.config(:development) # Load specified environment configuration
config = PayPal::SDK::Core::Config.config(:development, :app_id => "XYZ") # Override configuration

# Create HTTP object
http      = PayPal::SDK::Core::HTTP.new
http      = PayPal::SDK::Core::HTTP.new(:development)
http      = PayPal::SDK::Core::HTTP.new("svcs.sandbox.paypal.com", 443)

# To make API request
response  = http.get("/AdaptivePayments/GetPaymentOptions")

# Include Core package
include PayPal::SDK::Core
set_config :development # Set configuration
config  				# access configuration
logger  				# access logger
```