# OAuth

The Mapillary API lets you interect with Mapillary on the behalf of a user. This is achived by using OAuth 2.0. Mapillary supports the implicit and code flow of the OAuth [2.0 specification](http://tools.ietf.org/html/rfc6749).

Mapillary OAuth tokens do not have any expiration time. The user can at any time revoke the token directly from the settings page..

## Request Authorization

> Example initiation URL:

```curl
http://www.mapillary.com/connect?client_id=<CLIENT_ID>&response_type=token&scope=user:email%20org:read&redirect_uri=http:%2F%2Fexample.com`
```

The OAuth2 authorization endpoint. Your app redirects a user to this endpoint, allowing them to delegate access to their account.

`GET http://www.mapillary.com/connect`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
client_id | string | The client id belonging to your application
redirect_uri | string | The redirect uri you have configured for your application
response_type | enumeration | (code, implicit)
scope | string | The scopes to request from the user using %20 (space) as delimiter
state | string | Any value included here will be appended to the redirect URI

## Finish Authorization

The OAuth2 token endpoint. This endpoint accepts POST requests and is used to provision access tokens once a user has authorized your application.

### HTTP Request

`POST https://a.mapillary.com/v2/oauth/token`

Parameter | Type | Description
--------- | ------- | -----------
client_id | string | The client id belonging to your application
client_secret | string | The client secret belonging to your application
redirect_uri | string | The redirect uri you have configured for your application
grant_type | enumeration | (authorization_code)
code | string | The authorization code obtained when user is sent to redirect_uri

## Scopes

The following scopes are availble.

Name | Description
---- | -----------
mapillary:user    | This scope is only availble to native Mapillary applications
user:read         | Access to all private information about user
user:write        | Ability to update a users information
user:email        | Access to users email
public:write      | Update users public objects
public:upload     | Upload public images on behalf of the user
private:read      | Read users private objects
private:write     | Update users private objects
private:upload    | UPload private images for the user
org:read          | Read users organizations and projects
org:write         | Update users organizations and projects

