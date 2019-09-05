---
title: Auth0 and Sign In with Apple Overview
description: Understand how native login functionality works with Auth0 and your applications. 
connection: Apple
index: 3
image: /media/connections/apple.svg
seo_alias: apple
topics:
  - authentication
  - connections
  - social
  - native-social
contentType: concept
useCase:
  - add-login
  - customize-connections
  - add-idp
  - add-native-social
---
# Auth0 and Sign In with Apple Overview

Sign In with Apple is built on top of the [OAuth 2.0 Token Exchange specification](https://tools.ietf.org/html/draft-ietf-oauth-token-exchange-16). Auth0 created a profile to handle the following flow:

![Sign In with Apple Flow](/media/articles/connections/social/apple/siwa-concepts.png)

1. User authenticates via the identity provider's SDK on their iPhone/iPad. They receive an authorization code.
2. The application calls Auth0's `/oauth/token` endpoint with the following parameters:
    - `subject_token`: the authorization code they received above
    - `subject_token_type`: `http://auth0.com/oauth/token-type/apple-authz-code`
    - `grant_type`: `urn:ietf:params:oath:grant-type:token-exchange`
    - `client_id`: their Auth0 Client ID
    - `audience` and `scope` as needed (optional)
3. Auth0 exchanges the `code` with the identity provider for a set of ID, access, and refresh tokens.
4. Auth0 saves the user profile, executes rules and authorization, then issues access tokens (refresh tokens and ID tokens) as requested. These tokens are used to protect your APIs and users managed by Auth0.

## Grant types

### Native apps using token exchange 

### Web apps using oauth flow

## Logs

## Rate limits

## Application types that use Sign In with Apple and Auth0

* [Add Sign In with Apple to Your Native App](/connections/social/apple/native-app-siwa)
* [Add Sign In with Apple to Your Web App](/connections/social/apple/web-app-siwa)