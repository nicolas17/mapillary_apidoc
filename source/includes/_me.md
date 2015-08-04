# Me /me

## GET /me

> /v2/me

```curl
curl "https://a.mapillary.com/v2/me?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "about": "A short text about me.",
  "avatar": "22b939a6ac2e3920a434c0d9/profile.png",
  "member_since": 1379530348000,
  "username": "gyllen",
  "user_uuid": "2BJl04nvnfW1y2GNaj7x5w",
  "email": "email@example.com"
}
```

Get info about user.

### Scopes

Name | When
-----|-----
user:read | Always
user:email | Access to users email

### HTTP Request

`GET https://a.mapillary.com/v2/me`

### Response Parameters

Parameter | Description
--------- | -----------
about | Text about user
avatar | Url to user avatar
member_since | When user created account in EPOCH ms
username | Username of user
user_uuid | Unqiue identifier of user in Mapillary system
email | Users email if correct scope is authenticated

## PUT /me

TBD not yet availble.

## GET /me/feed

> /v2/me/feed

```curl
curl "https://a.mapillary.com/v2/me/feed?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "feed": [
    {
      "action": "commented",
      "timestamp": 1396244855000,
      "object": "comment",
      "key": "kKQR3646GpRnbqZSFvVlNA",
      "user": "gyllen",
      "other_user": "jesolem",
      "image_url": "https://d1cuyjsrcm0gby.cloudfront.net/kKQR3646GpRnbqZSFvVlNA/thumb-320.jpg",
      "main_description": "Whoa, this is a comment.",
      "detail_description": "",
      "location": "Lomma, Sweden",
      "version": 1
    }
  ]
}
```

Retrive a users feed.

### Scopes

Name | When
-----|-----
user:read | Always

### HTTP Request

`GET https://a.mapillary.com/v2/me/feed`

Parameter | Description
--------- | -----------
version | Get only feed items with this version and below
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
feed | Array of events in the feed sorted by newest first
feed[action] | Action or feed event
feed[timestamp] | When event happend
feed[object] | Type of object operetared at
feed[key] | Key of object
feed[user] | User responsible for action
feed[other_use] | Secondary user in action
feed[image_url] | Link to an image representing the event
feed[main_description] | Main description
feed[detail_description] | Longer and more detailed description of event
feed[location] | Location where event happend
feed[version] | Version of feed event

## GET /me/uploads/secrets

> /v2/me/uploads/secrets

```curl
curl "https://a.mapillary.com/v2/me/uploads/secrets?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "images_policy": "AAA",
    "images_hash": "BBB",
    "videos_policy": "CCC",
    "videos_hash": "DDD"
}
```

Retrive user specific hashes to use S3 direct upload for images.

### Scopes

Name | When
-----|-----
public:upload | Always

### HTTP Request

`GET https://a.mapillary.com/v2/me/uploads/secrets`

### Response Parameters

Parameter | Description
--------- | -----------
images_policy | Policy to upload to Mapillary images S3 folder
images_hash | Hash to upload to Mapillary images S3 folder
videos_policy: Policy to upload to Mapillary videos S3 folder
videos_hash: Hash to upload to Mapillary videos S3 folder

## GET /me/uploads/status

> /v2/me/uploads/status

```curl
curl "https://a.mapillary.com/v2/me/uploads/status?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
}
```

INFO

### Scopes

Name | When
-----|-----
public:upload | Always

### HTTP Request

`GET https://a.mapillary.com/v2/me/uploads/status`

### Response Parameters

Parameter | Description
--------- | -----------

## POST /me/uploads/images/:key

> /v2/me/uploads

```curl
curl "https://a.mapillary.com/v2/me/uploads/images/:key?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
}
```

INFO

### Scopes

Name | When
-----|-----
public:upload | Always

### HTTP Request

`POST https://a.mapillary.com/v2/me/uploads/images/:key`

### Response Parameters

Parameter | Description
--------- | -----------

## DELETE /me/uploads/images/:key

> /v2/me/uploads/images/:key

```curl
curl "https://a.mapillary.com/v2/me/uploads/images/:key?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
}
```

INFO

### Scopes

Name | When
-----|-----
public:upload | Always

### HTTP Request

`DELETE https://a.mapillary.com/v2/me/uploads/images/:key`

### Response Parameters

Parameter | Description
--------- | -----------

## DELETE /me/uploads/images/:key/file

> /v2/me/uploads/images/:key/file

```curl
curl "https://a.mapillary.com/v2/me/uploads/images/:key/:file?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
}
```

INFO

### Scopes

Name | When
-----|-----
public:upload | Always

### HTTP Request

`GET https://a.mapillary.com/v2/me/uploads/images/:key/:file`

### Response Parameters

Parameter | Description
--------- | -----------
