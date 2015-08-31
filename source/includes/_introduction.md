# Introduction

> Introduction

```curl
```
>

This is version 2 (v2) of the Mapillary API. Using this API you can access the vast amount of images and image sequences that are a part of Mapillary. Mapillary is a service for crowdsourcing map images using simple tools like smartphones or action cameras.

The APIs use OAuth2 for authentication and enable you and your applications to perform a wide range of tasks, as users or as apps acting on behalf of users.

At the moment we do not have any bindings, but we will make sure to get that going pretty soon.

# Bugs

## API

Please report bugs on API [here](https://github.com/mapillary/mapillary_issues).

## Documentation

Please report bugs or send pull requests on documentation [here](https://github.com/mapillary/mapillary_apidoc).

# Authentication

## client_id

> Provide a client_id in the query string:

```curl
# Always pass your client_id in the query string
curl https://a.mapillary.com/v2/status?client_id=<CLIENT_ID>
```

> Make sure to replace `<CLIENT_ID>` with your API key.

Mapillary uses a client id to allow access to the API. You can register a client at your [application settings page](http://www.mapillary.com/map/settings/applications). The Mapillary API expects that the client_id parameter is present in all requests.

Like this:

`https://a.mapillary.com/v2/status?client_id=<CLIENT_ID>`

<aside class="notice">
You must replace `<CLIENT_ID>` with your personal client id.
</aside>

## oauth token

> For authenticating request, make sure to add an authorization token in the parameters.

```curl
# Add the oauth token in the Authorization header
curl -H "Authorization: Bearer xxx.yyy.zzz" https://a.mapillary.com/v2/status?client_id=<CLIENT_ID>
```

> Make sure to replace `xxx.yyy.zzz` with the user's token.

The token received on behalf of the user is used to authenticate requests. Always pass the token in the http header "Authorization". As in this example:

`Authorization: Bearer xxx.yyy.zzz`

<aside class="notice">
You must replace `xxx.yyy.zzz` with the users token.
</aside>
