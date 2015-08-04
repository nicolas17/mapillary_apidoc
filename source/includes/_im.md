# Images /im

> /v2/im

Manage single images. For the ability to search for images see the seperate search API.

## GET /im/:key

> /v2/im/:key

```curl
curl "https://a.mapillary.com/v2/im/V3HG0CMVMk4aNQj6_YFHgQ?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "ca":95.70099,
  "captured_at":1400486721000,
  "key":"V3HG0CMVMk4aNQj6_YFHgQ",
  "lon":-118.369883,
  "lat":34.095438,
  "location":"De Longpre Avenue, L.A.",
  "user":"gyllen"
}
```

Retrive information about a specific image.

### Scopes

Name | When
-----|-----
private:read | Needed when accessing private images

### HTTP Request

`GET https://a.mapillary.com/v2/im/:key`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get information about

### Response Parameters

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
captured_at | Time image was captured in EPOCH ms
key | Key of the image
lon | Longitude of image
lat | Latitude of image
location | String representation of where image was shot
user | Username of user taken the image

## GET /im/:key/geojson

> /v2/im/:key/geojson

```curl
curl "https://a.mapillary.com/v2/im/V3HG0CMVMk4aNQj6_YFHgQ/geojson?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "features": [
    {
      "type":"Feature",
      "geometry": {
        "type":"Point",
        "coordinates": [
          -118.369883,
          34.095438
        ]
      },
      "properties": {
        "key":"V3HG0CMVMk4aNQj6_YFHgQ",
        "ca":95.70099
      }
    }
  ],
  "type":"FeatureCollection"
}
```

Retrive information about a specific image in geojson format.

### Scopes

Name | When
------|-----
private:read | Needed when accessing private images

### HTTP Request

`GET https://a.mapillary.com/v2/im/:key/geojson`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get information about

### Geojson Properties

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /im/:key/b

> /v2/im/:key/b

```curl
curl "https://a.mapillary.com/v2/im/:key/b?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "bs": [
        {
            "type": "license",
            "rect": [
                0.25625,
                0.7426944478352865,
                0.28875,
                0.7926944478352864
            ]
        },
        {
            "type": "useredit",
            "rect": [
                0.9425,
                0.6810277811686198,
                0.97,
                0.7210277811686198
            ]
        }
    ]
}
```

Retrive blurs for an image.

### Scopes

Name | When
------|-----
private:read | Needed when accessing private images

### HTTP Request

`GET https://a.mapillary.com/v2/im/:key/b`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get information about

### Response Parameters

Parameter | Description
--------- | -----------
bs | List of blurs for image
bs[type] | Describes type of blur, face = face detected, license = license plate detected, user = user defined blur
bs[rect] | Placement of blur as a rectangle, [SouthWest, NorthEast] -> [[x,y],[x,y]]
pbs | List of requested blurs, new requests can not be done until this requested is rejected or approved
pbs[type] | Describes type of blur, user = user defined blur
pbs[rect] | Placement of blur as a rectangle, [SouthWest, NorthEast] -> [[x,y],[x,y]]
user | User who decided the blur, if null its mapillary default
requesting_user | User requesting a blur

## POST /im/:key/b

> /v2/im/:key/b

```curl
curl -d "https://a.mapillary.com/v2/im/:key/b?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Request blur for an image.

### Scopes

Name | When
------|-----
public:write | Needed when writing to public images
private:write | Needed when writing to private images

### HTTP Request

`POST https://a.mapillary.com/v2/im/:key/b`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get information about

### Request body

> Request body example

```json
{
    "bs": [
        {
            "type": "license",
            "rect": [
                0.25625,
                0.7426944478352865,
                0.28875,
                0.7926944478352864
            ]
        },
        {
            "type": "useredit",
            "rect": [
                0.9425,
                0.6810277811686198,
                0.97,
                0.7210277811686198
            ]
        }
    ]
}
```

Parameter | Description
--------- | -----------
bs | List of blurs to send (including old blurs this is all blurs that are requested)
bs[type] | Describes type of blur, face = face detected, license = license plate detected, user = user defined blur
bs[rect] | Placement of blur as a rectangle, [SouthWest, NorthEast] -> [[x,y],[x,y]]

## GET  /im/:key/cm

> /v2/im/:key/cm

```curl
curl -d "https://a.mapillary.com/v2/im/:key/cm?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "cms": [
        {
            "comment": "Beautiful images, strange I have not seen this before.",
            "created_at": 1436485760094,
            "key": "PazK_LSDLAqcc3PdCAeeOA",
            "user": {
                "username": "gyllen",
                "avatar": "22b939a6ac2e3920a434c0d9/profile.png"
            }
        }
    ]
}
```

Get all comments for an image.

### Scopes

Name | When
------|-----
private:read | Needed when accessing private images

### HTTP Request

`POST https://a.mapillary.com/v2/im/:key/cm`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get information about

### Response Parameters

Parameter | Description
--------- | -----------
comment | The actual comment
created_at | When comment was commented in EPOCH ms
key | Uniq key of comment, this key could be used to delete comment
user{} | Struct of user
user[username] | Username of user
user[avatar]| Link to avatar of user

## POST /im/:key/cm

> /v2/im/:key/cm

```curl
curl "https://a.mapillary.com/v2/im/-l5NpA-2oGhmslXVYK6Y9g/cm?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Create a comment.

### Scopes

Name | When
-----|-----
public:write | When creating a user comment on a public image
private:write | When creating a user comment on a private image

### HTTP Request

`POST https://a.mapillary.com/v2/im/:key/cm`

Parameter | Description
--------- | -----------
key | Key of the image to comment on

### Request body

Parameter | Description
--------- | -----------
cm | The actual comment

## POST /im/:key/complain

> /v2/im/:key/complain

```curl
curl "https://a.mapillary.com/v2/im/-l5NpA-2oGhmslXVYK6Y9g/complain?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Create a complain on an image.

### HTTP Request

`POST https://a.mapillary.com/v2/im/:key/complain`

Parameter | Description
--------- | -----------
key | Key of the image to complain on

### Request body

Parameter | Description
--------- | -----------
cm | The complain to report (a comment)

## GET /im/:key/or

> /v2/im/:key/or

```curl
curl "https://a.mapillary.com/v2/im/:key/or?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "ca": 256.4223844427362,
    "captured_at": 1400317595000,
    "key": "2SCoJAJIjJFB4bK2m3mspg",
    "lon": 13.01069653,
    "lat": 55.60790127,
    "user": "mapillarysweden1",
    "or_rects": [
        {
            "score": "0.935301527552",
            "package": "trafficsign_eu_1.0",
            "type": "information_pedestrian_crossing",
            "rect": [
                0.3037109375,
                0.5182291666666666,
                0.3232421875,
                0.5442708333333334
            ]
        },
        {
            "score": "1.66795574937",
            "package": "trafficsign_eu_1.0",
            "rect": [
                0.302734375,
                0.5494791666666666,
                0.326171875,
                0.5807291666666666
            ],
            "type": "mandatory_keep_right"
        }
    ],
    "or_rectversions": [],
    "or_done": true,
    "or_packages": [
        "trafficsign_eu_1.0"
    ]
}
```

Retrive recognized objects for an image.

### Scopes

Name | When
------|-----
private:read | Needed when accessing private images

### HTTP Request

`GET https://a.mapillary.com/v2/im/:key/or`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the image to get objects for

### Response Parameters

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
captured_at | Time image was captured in EPOCH ms
key | Key of the image
lon | Longitude of image
lat | Latitude of image
user | Username of user taken the image
or_rects[] | Matches in form of rectangles
or_rects[score] | Confidence score of match
or_rects[package] | Object recognition package
or_rects[type] | Classification of match
or_rects[rect] | Rectangle of match in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]
or_rectversions[] | User classifications
or_rectversions[rects] | Detections in form of rectangles
or_rectversions[rects][rect] | Rectangle of detection in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]
or_rectversions[rects][type] | Type of match
or_rectversions[rects][user_defined] | True if defined by user
or_rectversions[timestamp] | Version and also timestamp of registred version match agains confirmations
or_rectversions[user] | User performing detection
or_rectversions[package] | Package feedbacking against
or_done | True if all detections are run on image
or_packages | List of detections thats been run on image
or_confirmed_packages[] | Conformations against detections
or_confirmed_packages[package] | Package confirmation is made against
or_confirmed_packages[user] | User performing confirmations
or_confirmed_packages[version] | Version of detection that is confirmed

## POST /im/:key/or/version

Create a detected version. Not yet availble.

## POST /im/:key/or/version/approve

Approve a detected version. Not yet availble.
