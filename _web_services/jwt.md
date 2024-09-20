---
name: jwt
title: How to use JWTs with SESAR
layout: default
order: 3
---

## JSON Web Tokens (JWT) and SESAR

A JWT is a pair of secret tokens used to authenticate with the SESAR Webservices.

There are 2 different tokens created when you request a JWT:
- **Access Token**: A short lived token used to authenticate during API calls.
- - Access tokens will be **valid for 1 day** before needing to be refreshed.
- **Refresh Token**: A longer lived token used to create a new access token when the previous token has expired.
- - Refresh tokens will be **valid for 30 days**.
- - Refresh tokens will be **rotated upon use**, meaning using a refresh token to retrieve a new access token will also give you a new refresh token. This new refresh token will have a reset expiration period (30 days), while the original refresh token will be revoked and no longer valid.


## Generating your Token Pair
In order to generate and use JSON Web Tokens with the SESAR webservices, you **must use ORCID** when logging into MySESAR. Geopass is being deprecated and will not be supported for new features.
- Sign in with ORCID
- Visit Developer Settings in your [MySESAR profile page](https://app.geosamples.org/views/my_profile.php)
- Select "Generate a New Token" and you should see the following: 

![Image](../assets/images/jwt.png)

**NOTE: NEVER SHOW YOUR JSON WEB TOKEN LIKE THIS. A JWT allows whoever holds it to access the SESAR system as you**

## Usage

When using one of the webservices that requires authentication, you can use the access token in the authorization header:

```
curl \
  -H "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN" \
  https://app.geosamples.org/webservices/credentials_service_v2.php
```

## Refreshing your JWT
When your short-lived access token expires, you can use the longer-lived refresh token to obtain another access token.
```
curl \
  -X POST \
  -H "Content-Type: application/json" \
  -d '{"refresh":"YOUR_JWT_REFRESH_TOKEN"}' \
  https://app.geosamples.org/webservices/refresh_token.php
```

### Responses
- **200** Successful. Refresh token is valid. 

```
{
    "access": "YOUR_NEW_ACCESS_TOKEN",
    "refresh": "YOUR_NEW_REFRESH_TOKEN"
}
```

- **401** Unauthorized - An authentication failure will return text as following.

```
{
    "detail": "Token is invalid or expired",
    "code": "token_not_valid"
}
```


## Revoking a JSON Web Token
If you suspect your token or tokens have been compromised, you may revoke them. 

To do so, simply select the "Revoke All JWTs" button and confirm your selection.

This will result in all JWTs generated under your user account to be invalidated. Be careful as this may cause any scripts or applications using that token to lose access to SESAR webservices.