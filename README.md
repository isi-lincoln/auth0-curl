auth0-curl
==========

A simple wrapper that calls Auth0 (more specifically `/oauth/token`) and retrieves a JWT
Authorization header for you.

# Setup
- Create a .passwd file with the following structure:
```
AUTH0_CLIENTID
AUTH0_USERNAME
AUTH0_PASSWORD
```

- Modify AUTH0_DOMAIN in script to point to your domain


# Usage
``` ./curl-auth0 ```

# How it works
Behind the scenes, this will do:

1. a call to Auth0 `/oauth/token`
2. get the result (a JWT) that looks like this: `{"id_token":"xxx.yyy.zzz","access_token":"aaaaaaaaaaaaaaaa","token_type":"bearer"}`
3. extract the `access_token` from the JWT
4. call curl:

```
curl -H "authorization: bearer `./curl-auth0`" https://localhost:80
```
