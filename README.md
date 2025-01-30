# Omniauth::MicrosoftV2Auth

Microsoft V2 OAuth2 Strategy for OmniAuth.
Can be used to authenticate with Microsoft Services and get a token for the Microsoft Graph Api.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'omniauth-microsoft_v2_auth'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omniauth-microsoft_v2_auth

## Usage

```ruby
Rails.application.config.middleware.use OmniAuth::Builder do
  provider :microsoft_v2_auth, ENV['AZURE_APPLICATION_CLIENT_ID'], ENV['AZURE_APPLICATION_CLIENT_SECRET']
end
```

## Publishing

This is a public repo, so we don't need to publish the gem in order to pull the changes into an application. Add this line to your Gemfile to get this gem: `gem "omniauth-microsoft_v2_auth", github: "bonusly/omniauth-microsoft_v2_auth"`

When you have changes that you want to pull into an app (i.e. something you would publish as a new version), you can just run `bundle update omniauth-microsoft_v2_auth` in the repo.
