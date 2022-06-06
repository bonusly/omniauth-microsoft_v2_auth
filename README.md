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

To publish to our private gemserver you will first need to get the api key.

The api key can be found in vault: https://vault.bonus.ly/ui/vault/secrets/kv/show/global/gemstash

To set it correctly first check to see if you already have a file at `~/.gem/credentials` if you do
you can skip to editing that file. If not follow these steps to create it:

```shell
$ mkdir -p ~/.gem
$ touch ~/.gem/credentials
$ chmod 0600 ~/.gem/credentials
```

Once you have a credentials file you will need to add the following line to it:

```yaml
---
:private_gemserver_key: <API KEY GOES HERE>
```

Now that you have the credentials configured use the following command to push a new version to the private gemserver:

```shell
$ gem push --key private_gemserver_key --host https://rubygems.bonusly.dev/private pkg/omniauth-microsoft_v2_auth-X.X.X.gem
```

Now you can have the applications which use this gem run bundle update to get the new version.
