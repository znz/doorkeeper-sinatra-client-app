# doorkeeper-sinatra-client-app

This is a simple demo oauth2 client for doorkeeper gem.

## Usage

### Doorkeeper gem side

```ruby
application = Doorkeeper::Application.create!(
  name: 'Sample Client',
  redirect_uri: 'http://localhost:4567',
  scopes: 'public sample',
)
puts "CLIENT_ID=#{application.uid}"
puts "CLIENT_SECRET=#{application.secret}"
```

### Client site

```
git clone https://github.com/znz/doorkeeper-sinatra-client-app
cd doorkeeper-sinatra-client-app
bundle install
export CLIENT_ID=above_id
export CLIENT_SECRET=above_secret
export OAUTH2_SCOPE="public sample"
ruby oauth2-app.rb
open http://localhost:4567/
```

## WARNING

- Tokens should not show to browsers, but this demo app shows tokens for debug. So this is not for production use.

## misc

- If you use `dotenv`, see `example.env` for example.
- If you enable PKCE on doorkeeper gem side, you can use `pkce-app.rb` too.

## LICENSE

MIT License
