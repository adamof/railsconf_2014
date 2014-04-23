Service oriented authentication
===
Jeremy Green

OAuth 2

Introducing Mc-SOA (monolith centric - soa)

Cloud HDR
- hdr photo processing automation


Goals and requirements
- small focused apps
- single sign on/off
- minimize code duplication
- support a variety of app/service types

Brief overview OAuth 2
- GET /protected
- Fails and redirects to OAuth provider. can you please see who 
that is and let me know
- POST /oauth/token?...
- App and OAuth provider exchange tokens and information about the 
user
- Finally consumer redirects to /protected
- 200 OK

doorkeeper-gem/doorkeeper
consumer: omniauth

idea - build a gem that exposes an interface between oauth provider
and consumer. then integrate that gem in your multiple apps. Expect also
the same routes for authentication are always available on other services

consumer implementation - part 1

- create a rails engine 
  - dependencies: omniauth / omniaut-oauth2
  - feed it information where provider lives and how to find it
  - register the strategy with omniauth

provider implementation
- gem 'doorkeeper'
- implements login page if user not authenticated
- implement skip_authorization if you do not need
to warn users you want to authorize consumer X to 
get your details
- doorkeeper returns token when authenticated

consumer implementation - part 2
- process the the auth_token
- implement callbacks to exit the oauth login process
  - /oauth/:provider/callback
  - /oauth/failure
- if user does not exist it creates a new user from
the payload json
- redirect user to /protected resource


### single sign off

We need to implement single sign off too (omniauth and doorkeeper do
not implement this )
- on the provider, implement a remove user cookie ( so the consumer can see
someone logged out ) 
- on the consumer side
  - check if the cookie is present and valid, and if cookie
  info matches with the current session. 
  - implement a logout route and redirect to the provider url


### final implementation

on the provider we need to add info for each consumer so we are certain
only "our" consumers are valid. Doorkeeper will return specific info that
should be put as specific consumer env vars

