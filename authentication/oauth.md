# OAuth resources

* [The OAuth Bible](http://oauthbible.com/)  

Notes from the OAuth intro meeting:

## OAuth 1.0
* old, deprecated 
* user receives token from service that doens't expire, but can be deleted
* tokens susceptible to interception

## OAuth 2.0
* new, supported 
* 2 types of tokens: refresh token & access token?
* user calls the service, the service returns a code, different token depending on permissions
* tokens can be required or optional (differently scoped permissions); one-time token - the app sends it to the service with the access token that is time-limited
* the access token is stored on the user; access token is required for a server response (?)
* refresh token endpoint gets called when access token expires - returns a new access token if the user is valid? 
* performance impact - on slow APIs, considerable; otherwise fairly standard
* access token needs to be persisted in memory
* key-value store in Redis, shared over however many dynos are running it
* two connections to each entity that requires authorisation (external service API etc)

[Omniauth](https://github.com/omniauth/omniauth-oauth2) - Ruby library for OAuth.

## Basic auth flow

> Application is registered with intended provider(i.e. Google, Facebook, GitHub, etc) and a `client_id` and `client_secret` are obtained
> Application sends out a request to the provider (i.e. Google, Facebook, GitHub, etc) including the application’s `client_id` and `client_secret`
> Provider asks the user if they’d like to authorize the application to access their personal info
> If yes, the provider sends back a token/code to `/auth/:provider/callback`, a route found in the application
> The application sends out a 2nd request to the provider with the token/code
> The provider sends a response back with a user’s information
> The application parses the response to create a hash of user info

[Source - also includes good Omniauth info](https://medium.com/@ali_schlereth/omniauth-is-not-a-scary-monster-a23b21c4f739)

