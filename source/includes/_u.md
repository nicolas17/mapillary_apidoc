# User /u

> /v2/u

Get public information and stats about Mapillary users.

## GET /u/:user

> /v2/im/:user

```curl
curl "https://a.mapillary.com/v2/u/gyllen?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "about":"I work in the deep dark mines of Mapillary.",
  "avatar":"https://d4vkkeqw582u.cloudfront.net/bf9970c0c76a3fe226aa212e/profile.png",
  "distance_all":518570,
  "histogram": [
    {
      "day":1381622400000,
      "count":295
    },
    {
      "day":1381708800000,
      "count":152
    }
  ],
  "images_none_processed":0,
  "images_hidden":28,
  "images_all":21606,
  "user":"gyllen",
  "user_uuid":"2BJl04nvnfW1y2GNaj7x5w"
}
```

Retrieve public information and stats about a Mapillary user.

### Scopes

none

### HTTP Request

`GET https://a.mapillary.com/v2/u/:user`

Parameter | Description
--------- | -----------
user | Username of user wanted for lookup

### Response Parameters

Parameter | Description
--------- | -----------
about | Descriptive user entered text about user
avatar | Users avatar image
distance_all | Distance mapped in meters by user
histogram | Users uploads the last year, day by day
images_none_processed | Public images uploaded that entered the Mapillary system but are not fully processed
images_hidden | Public images hidden by user
images_all | Total amount of public images uploaded by user
user | username
user_uuid | Unique user identifier in the Mapillary system

## GET /u/:user/feed

> /v2/im/:user/feed

```curl
curl "https://a.mapillary.com/v2/u/gyllen/feed?client_id=<CLIENT_ID>"
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

Retrieve a users feed.

### HTTP Request

`GET https://a.mapillary.com/v2/u/:user/feed`

Parameter | Description
--------- | -----------
user | Username of user to get connections for
version | Get only feed items with this version and below
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
feed | Array of events in the feed sorted by newest first
feed[action] | Action or feed event
feed[timestamp] | When event happened
feed[object] | Type of object operated at
feed[key] | Key of object
feed[user] | User responsible for action
feed[other_use] | Secondary user in action
feed[image_url] | Link to an image representing the event
feed[main_description] | Main description
feed[detail_description] | Longer and more detailed description of event
feed[location] | Location where event happened
feed[version] | Version of feed event

## GET /u/:user/profile.png

> /v2/im/:user/profile.png

```curl
curl "https://a.mapillary.com/v2/u/gyllen/profile.png?client_id=<CLIENT_ID>"
```

> The above command redirects to the users profile picture

Retrieve a users profile image.

### HTTP Request

`GET https://a.mapillary.com/v2/u/:user/profile.png`
