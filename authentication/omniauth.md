# Omniauth

[Source](https://medium.com/@ali_schlereth/omniauth-is-not-a-scary-monster-a23b21c4f739)

[view the basic auth flow here](../authentication/oauth.md)

## Omniauth flow:

1. Register your app with intended provider, obtain your `client_id` and `client_secret`
2. In `config/initializers/omniauth.rb`:

```
Rails.application.config.middleware.use OmniAuth::Builder do
   provider :github, ENV['GITHUB_ID'], ENV['GITHUB_SECRET']
end
```

or, optional hash of scoping options:

```
Rails.application.config.middleware.use OmniAuth::Builder do  
   provider :google_oauth2, ENV["GOOGLE_CLIENT_ID"],
                            ENV["GOOGLE_CLIENT_SECRET"],
   {    :name => "google",
        :scope => ['contacts', 'plus.login', 'plus.me', 'email',
                   'profile'],    
        :prompt => "select_account",
        :image_aspect_ratio => "square",
        :image_size => 50,
        :access_type => 'offline'  }
end
```

3. in `routes.rb`:

```
get 'auth/provider_name', as: 'provider_name_login'
get '/auth/:provider/callback', to: 'sessions#create'
```

4. In view, the login link will look like: `<=% link_to "Login", provider_name_login_path %>`
5. User clicks this link, is redirected to the provider, provider asks for permission to send the user's info
6. User okays; Omniauth provides this in its `sessions#create`:

```
def create
   user_info = request.env['omniauth.auth']
   ..find_or_create_by user using user_info as you see fit..
end  
```

👆the `request.env[‘omniauth.auth’]` is a hash of user information sent back from the provider

* [Docs](https://github.com/omniauth/omniauth)
* [Good SO explainer on the subject](https://stackoverflow.com/questions/848591/how-do-i-access-the-rack-environment-from-within-rails)
