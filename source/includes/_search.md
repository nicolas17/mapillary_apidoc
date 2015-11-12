# Search /search

> /v2/search

Search for objects in the Mapillary archives.

## GET /search/b

> /v2/search/b

```curl
curl "https://a.mapillary.com/v2/search/b?client_id=<CLIENT_ID>&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "ims" : [
    {
      "ca":165.9576,
      "captured_at":1412953933000,
      "key":"66AuTgR_tQKBuO07rLPIWg",
      "lon":28.357766,
      "lat":-15.400321,
      "location":"Lusaka",
      "user":"gyllen"
    }
  ]
}
```

Search for blurs to approve/reject.

### Scopes

Name | When
------|-----
private:read | Needed to get private images

### HTTP Request

`GET http://a.mapillary.com/v2/search/b`

Parameter | Description
--------- | -----------
client_id | The client id of your application
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------

## GET /search/im

> /v2/search/im

```curl
curl "https://a.mapillary.com/v2/search/im?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "ims" : [
    {
      "ca":165.9576,
      "captured_at":1412953933000,
      "key":"66AuTgR_tQKBuO07rLPIWg",
      "lon":28.357766,
      "lat":-15.400321,
      "location":"Lusaka",
      "user":"gyllen"
    }
  ]
}
```

Search for images.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more images in pagination false if not.
ims | A list of images
ims[ca] | Angle of the image shot in degrees between 0 to 360
ims[captured_at] | Time image was captured in EPOCH ms
ims[key] | Key of the image
ims[lon] | Longitude of image
ims[lat] | Latitude of image
ims[location] | String representation of where image was shot
ims[user] | Username of user taken the image

## GET /search/im/close

> /v2/search/im/close

```curl
curl "https://a.mapillary.com/v2/search/im/close?client_id=<CLIENT_ID>&lat=55.874973779667876&limit=1&lon=12.981805801391602&min_ca=140&max_ca=190"
```

> The above command returns JSON structured like this:

```json
  {
    "more": true,
    "ims" : [
      {
        "ca":165.9576,
        "captured_at":1412953933000,
        "distance":10,
        "key":"66AuTgR_tQKBuO07rLPIWg",
        "lon":28.357766,
        "lat":-15.400321,
        "location":"Lusaka",
        "user":"gyllen"
      }
    ]
  }
```

Get images close to a certain point defined by longitude, latitude, max angle, min angle and a radius in meters.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/close`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show all none projects
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
lat | Latitude to search in circle from
lon | Longitude to search in circle from
min_ca | Minimum angle of image in degrees
max_ca | Maximum angle of image in degrees
distance | Search radius in meters
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more images in pagination false if not.
ims | A list of images
ims[ca] | Angle of the image shot in degrees between 0 to 360
ims[captured_at] | Time image was captured in EPOCH ms
ims[distance] | Distance in meters for the closets image
ims[key] | Key of the image
ims[lon] | Longitude of image
ims[lat] | Latitude of image
ims[location] | String representation of where image was shot
ims[user] | Username of user taken the image

## GET /search/im/w3w

> /v2/search/im/w3w

```curl
curl "https://a.mapillary.com/v2/search/im/w3w?client_id=<CLIENT_ID>&string=bland.pylons.asserts"
```

> The above command returns JSON structured like this:

```json
  {
    "ims" : [
      {
        "key":"66AuTgR_tQKBuO07rLPIWg",
        "lon":28.357766,
        "lat":-15.400321
      }
    ]
  }
```

Get images in a specific w3w word

### Scopes

None

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/w3w`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
string | what3words string

### Response Parameters

Parameter | Description
--------- | -----------
ims | A list of images
ims[key] | Key of the image
ims[lon] | Longitude of image
ims[lat] | Latitude of image

## GET /search/im/randomselected

> /v2/search/im/randomselected

```curl
curl "https://a.mapillary.com/v2/search/im/randomselected?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "ca":165.9576,
  "captured_at":1412953933000,
  "distance":10,
  "key":"66AuTgR_tQKBuO07rLPIWg",
  "lon":28.357766,
  "lat":-15.400321,
  "location":"Lusaka",
  "user":"gyllen"
}
```

Get a random image from the Mapillary image archive, the images is randomized from a set of curated images.

### Scopes

none

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/randomselected`

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

## GET /search/im/b

> /v2/search/im/b

```curl
curl "https://a.mapillary.com/v2/search/im/b?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "blur": [
    {
      "type":"license",
      "rect": [
        0.7444852941176471,
        0.4959150326797386,
        0.8002450980392157,
        0.5175653594771242
      ]
    }
  ],
  "ca":165.9576,
  "captured_at":1412953933000,
  "distance":10,
  "key":"66AuTgR_tQKBuO07rLPIWg",
  "lon":28.357766,
  "lat":-15.400321,
  "location":"Lusaka",
  "user":"gyllen"
}
```

Search and get all image blurs within an area.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/b`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show all none projects
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more images in pagination false if not.
ims | A list of images
ims[blur] | List of current blurs for image
ims[blur][type] | Describes type of blur, face = face detected, license = license plate detected, user = user defined blur
ims[blur][rect] | Placement of blur as a rectangle, [SouthWest, NorthEast] -> [[x,y],[x,y]]
ims[ca] | Angle of the image shot in degrees between 0 to 360
ims[captured_at] | Time image was captured in EPOCH ms
ims[distance] | Distance in meters for the closets image
ims[key] | Key of the image
ims[lon] | Longitude of image
ims[lat] | Latitude of image
ims[location] | String representation of where image was shot
ims[user] | Username of user taken the image

## GET /search/im/cm

> /v2/search/im/cm

```curl
curl "https://a.mapillary.com/v2/search/im/cm?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "ca":165.9576,
  "captured_at":1412953933000,
  "comments": [
    {
      "comment": "Nice image",
      "created_at": 1404416754000,
      "key": "lPP2c_CMwtBvfLqiWc_NSw",
      "user": "jesolem"
    }
  ],
  "distance":10,
  "key":"66AuTgR_tQKBuO07rLPIWg",
  "lon":28.357766,
  "lat":-15.400321,
  "location":"Lusaka",
  "user":"gyllen"
}
```

Get all images that have at least one comment in an area.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/cm`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show all none projects
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more images in pagination false if not.
ims | A list of images
ims[comment] | List of comments for image
ims[comment][comment] | The actual comment
ims[comment][created_at] | When comment was commented in EPOCH ms
ims[comment][key] | Comment key to reference comment by
ims[comment][user] | User who made comment
ims[ca] | Angle of the image shot in degrees between 0 to 360
ims[captured_at] | Time image was captured in EPOCH ms
ims[distance] | Distance in meters for the closets image
ims[key] | Key of the image
ims[lon] | Longitude of image
ims[lat] | Latitude of image
ims[location] | String representation of where image was shot
ims[user] | Username of user taken the image

## GET /search/im/or

> /v2/search/im/or

```curl
curl "https://a.mapillary.com/v2/search/im/or?or_classes[]=prohibitory_no&or_classes[]=other_no&or_package=trafficsign_eu_1.0&min_score=2&client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "ims": [
    {
      "ca":119.65005493164062,
      "key":"O77SSbW100Il4NcIPU0-9Q",
      "lat":53.88683744240552,
      "lon":18.62872120924294,
      "rects": [
        {
          "package":"trafficsign_eu_1.0",
          "score":"0.810551672189",
          "type":"mandatory_go_straight",
          "rect":[
            0.70703125,
            0.4231770833333333,
            0.732421875,
            0.45703125
          ]
        }
      ],
      "user":"gyllen"
    }
  ]
}
```

Search for recognized objects in images. Currently these are traffic signs.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/or`


Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authorized user
me | Only objects in images from logged in user
user | Only objects in images from specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
or_package | Package to search in (available "trafficsign_eu_1.0" and "trafficsign_us_1.0")
or_classes[] | Arrays of classes to search for. Search works on prefix basis, so "prohibitory" will match both "prohibitory_no_parking" and "prohibitory_no_traffic_both_ways". While "prohibitory_no_parking" will only match "prohibitory_no_parking". For a list of classes see [Object Recognition Classes](/#object-recognition-classes)..
min_score | Minimal category score
limit | Results per page in pagination
page | Page number in pagination


### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more images in pagination false if not.
ims | List of images that include matches
ims[ca] | Angle of where images was taken
ims[key] | Key of image
ims[lat] | Latitude of image
ims[lon] | Longitude of image
ims[rects] | Matches in form of rectangles
ims[rects][package] | Object recognition package
ims[rects][score] | Confidence score of match
ims[rects][type] | Classification of match
ims[rects][rect] | Rectangle of match in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]
ims[user] | Username of user that provided the image


## GET /search/im/or/random

> /v2/search/im/or/random

```curl
curl "https://a.mapillary.com/v2/search/im/or/random?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "key": "D0OcUyPvenEDCwObI571LA",
  "rects": [
    {
      "package": "trafficsign_eu_1.0",
      "score": "0.0732049922895",
      "type": "mandatory_keep_right",
      "rect": [
        0.05078125,
        0.7291666666666666,
        0.0732421875,
        0.7591145833333334
      ]
    },
    {
      "package": "trafficsign_eu_1.0",
      "score": "0.0164618917635",
      "type": "prohibitory_speed_limit_60",
      "rect": [
        0.6865234375,
        0.75,
        0.7783203125,
        0.8802083333333334
      ]
    }
  ],
  "orversions": [
    {
      "timestamp": 1437218019615,
      "package": "trafficsign_eu_1.0",
      "user": "hknk1",
      "rects": []
    }
  ],
  "random_type": 1
}
```

Get a random recognized images with recognized object. Currently these are traffic signs.


### HTTP Request

`GET http://a.mapillary.com/v2/search/im/or/random`


Parameter | Description
--------- | -----------
client_id | The client id of your application


### Response Parameters

Parameter | Description
--------- | -----------
key | Key of the image
rects | Matches in form of rectangles
rects[package] | Object recognition package
rects[score] | Confidence score of match
rects[type] | Classification of match
rects[rect] | Rectangle of match in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]
orversions | List of recognition versions
orversions[timestamp] | Version and also timestamp of registered version match against confirmations
orversions[package] | Object recognition package
orversions[user] | user who created the version of the recognition
orversions[rects] | Matches in form of rectangles
orversions[rects][score] | Confidence score of match
orversions[rects][type] | Classification of match
orversions[rects][user_defined] | True if the object was defined by the user
orversions[rects][rect] | Rectangle of match in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]
random_type | ????

## GET /search/im/s/:key

> /v2/search/im/s/:key

```curl
curl "https://a.mapillary.com/v2/search/im/s/uwDS-P5HcC9BfMghANb3Pw?client_id=<CLIENT_ID>"
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

Search for an image given a sequence. If a point is provided (lat, lon), closest image will be returned.

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/s/:key`


Parameter | Description
--------- | -----------
key | A sequence key to use for the search
lat | Latitude to be close at
lon | Longitude to be close at

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

## GET /search/im/geojson

```curl
curl "https://a.mapillary.com/v2/search/im/geojson?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          12.44476,
          65.770999
        ]
      },
      "properties": {
        "ca": 144.747,
        "key": "T3vpeidB4_N1TX5O4fh9rw"
      }
    }
  ],
  "type": "FeatureCollection"
}
```

Search for images and return geojson.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/geojson`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /search/im/geojson/close

> /v2/search/im/geojson/close

```curl
curl "https://a.mapillary.com/v2/search/im/geojson/close?client_id=<CLIENT_ID>&lat=55.874973779667876&limit=1&lon=12.981805801391602&min_ca=140&max_ca=190"
```

> The above command returns JSON structured like this:

```json
{
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12.9807531619924,
                    55.8747099459846
                ]
            },
            "properties": {
                "ca": 147.372297838271,
                "key": "q0a6C3iEDjh3XUfGRmVPHQ"
            }
        }
    ],
    "type": "FeatureCollection"
}
```

Get images close to a certain point defined by longitude, latitude, max angle, min angle and a radius in meters in geojson format.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/geojson/close`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show all none projects
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
lat | Latitude to search in circle from
lon | Longitude to search in circle from
min_ca | Minimum angle of image in degrees
max_ca | Maximum angle of image in degrees
distance | Search radius in meters
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /search/im/geojson/randomimage

```curl
curl "https://a.mapillary.com/v2/search/im/geojson/randomimage?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "Point",
                "coordinates": [
                    13.2313177,
                    55.77544222
                ]
            },
            "properties": {
                "ca": 241.206534530401,
                "key": "MB7HcaQLeuCom53Uvez5yg"
            }
        }
    ],
    "type": "FeatureCollection"
}
```

Get a random image in geojson format.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/geojson/randomimage`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /search/im/geojson/b

```curl
curl "https://a.mapillary.com/v2/search/im/geojson/b?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          12.44476,
          65.770999
        ]
      },
      "properties": {
        "blurs" [],
        "ca": 144.747,
        "key": "T3vpeidB4_N1TX5O4fh9rw"
      }
    }
  ],
  "type": "FeatureCollection"
}
```

Search for images with blurs and return geojson.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/geojson/b`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
blurs | List of blurs
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /search/im/geojson/cm

```curl
curl "https://a.mapillary.com/v2/search/im/geojson/cm?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          12.44476,
          65.770999
        ]
      },
      "properties": {
        "commants": []
        "ca": 144.747,
        "key": "T3vpeidB4_N1TX5O4fh9rw"
      }
    }
  ],
  "type": "FeatureCollection"
}
```

Search for images and return geojson.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/geojson`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
comments | List of comments
ca | Angle of the image shot in degrees between 0 to 360
key | Key of the image

## GET /search/im/geojson/or

> /v2/search/im/or

```curl
curl "https://a.mapillary.com/v2/search/im/geojson/or?or_classes[]=prohibitory_no&or_classes[]=other_no&or_package=trafficsign_eu_1.0&min_score=2&client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "type": "FeatureCollection",
  "features": [
    {
      "type":"Feature",
      "geometry": {
        "type":"Point",
        "coordinates":[17.972541,59.295835]
      },
      "properties": {
        "key":"4IJdgEKP9lgmrMdAw776sA",
        "boundary": {
          "min_lat":59.295835,
          "max_lat":59.295835,
          "min_lon":17.972541,
          "max_lon":17.972541
        },
        "rects": [
          {
            "package":"trafficsign_eu_1.0",
            "score":"2.20829962158",
            "type":"other_no_entry",
            "rect": [
              0.943359375,
              0.58984375,
              0.96875,
              0.6328125
            ]
          }
        ]
      }
    }
  ]
}
```

Search for recognized objects in images.

### Scopes

Name | When
-----|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/im/or/geojson`


Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show all none projects
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
or_package | Package to search in (available "trafficsign_eu_1.0" and "trafficsign_us_1.0")
or_classes[] | Arrays of classes to search for. Search are on prefix "prohibitory" will match both "prohibitory_no_parking" and "prohibitory_no_traffic_both_ways". While "prohibitory_no_parking" will only match "prohibitory_no_parking". For a list of classes see [Object Recognition Classes](/#object-recognition-classes).
min_score | Minimal category score
limit | Results per page in pagination
page | Page number in pagination

### Geojson properties

Property | Description
--------- | -----------
key | Key of the image
boundary | Boundary fully covering the Geojson object
rects | Matches in form of rectangles
rects[package] | Object recognition package
rects[score] | Confidence score of match
rects[type] | Classification of match
rects[rect] | Rectangle of match in normalized coordinates (0 to 1) [North West X, North West Y, South East X, South East Y]

## GET /search/s

```curl
curl "https://a.mapillary.com/v2/search/s?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "ss": [
    {
      "boundary": {
        "min_lat": 55.881391,
        "min_lon": 12.998529,
        "max_lat": 55.881464,
        "max_lon": 12.999371
      },
      "captured_at": 1393974729000,
      "cas": [
        277.0169,
        276.5476,
        276.9955,
        282.9344,
        278.464,
        262.5792
      ],
      "coords": [
        [
          12.999371,
          55.881391
        ],
        [
          12.999269,
          55.881393
        ],
        [
          12.99903,
          55.881421
        ],
        [
          12.998885,
          55.881438
        ],
        [
          12.998721,
          55.881446
        ],
        [
          12.998529,
          55.881464
        ]
      ],
      "key": "VbAjo-zFc0-5MnLr9NGo3w",
      "keys": [
        "_OIeLo5yNx2t062lsRvY3g",
        "M1khnbbXaYMmy6R8E9qWnQ",
        "kASJKwnX8LqkCGvdZmNKVQ",
        "QVF-zyrwsIEi9ggQuIymzw",
        "hZwk1eIWOGe93CtLmZ4JMw",
        "zaDzim32bzYiwvN1vjrnYQ"
      ]
    }
  ]
}
```

Search for sequences.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/s`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more sequences in pagination false if not.
ss | A list of sequences
ss[boundary] | Box covering the whole sequence
ss[captured_at] | When the sequence was captured
ss[cas] | List of angles
ss[coords] | List of coords for the sequence
ss[key] | Key of the sequence
ss[keys] | Array of the keys of the images in the sequence

## GET /search/s/geojson

```curl
curl "https://a.mapillary.com/v2/search/s/geojson?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=1&page=0"
```

> The above command returns JSON structured like this:

```json
{
  "more": true,
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [
            12.999371,
            55.881391
          ],
          [
            12.999269,
            55.881393
          ],
          [
            12.99903,
            55.881421
          ],
          [
            12.998885,
            55.881438
          ],
          [
            12.998721,
            55.881446
          ],
          [
            12.998529,
            55.881464
          ]
        ],
        "bbox": [
          12.998529,
          55.881391,
          12.999371,
          55.881464
        ]
      },
      "properties": {
        "boundary": {
          "min_lat": 55.881391,
          "min_lon": 12.998529,
          "max_lat": 55.881464,
          "max_lon": 12.999371
        },
        "captured_at": 1393974729000,
        "key": "VbAjo-zFc0-5MnLr9NGo3w",
        "keys": [
          "_OIeLo5yNx2t062lsRvY3g",
          "M1khnbbXaYMmy6R8E9qWnQ",
          "kASJKwnX8LqkCGvdZmNKVQ",
          "QVF-zyrwsIEi9ggQuIymzw",
          "hZwk1eIWOGe93CtLmZ4JMw",
          "zaDzim32bzYiwvN1vjrnYQ"
        ],
        "cas": [
          277.0169,
          276.5476,
          276.9955,
          282.9344,
          278.464,
          262.5792
        ]
      }
    }
  ],
  "type": "FeatureCollection"
}
```

Search for sequences.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/s`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Geojson Properties

Parameter | Description
--------- | -----------
boundary | Box covering the whole sequence
captured_at | When the sequence was captured
key | Key of the sequence
keys | Array of the keys of the images in the sequence
cas | List of angles

## GET /search/s/ul

```curl
curl "https://a.mapillary.com/v2/search/s/ul?client_id=<CLIENT_ID>&max_lat=55.89&max_lon=13.01&min_lat=55.875&min_lon=12.975&limit=2&page=0"
```

> The above command returns JSON structured like this:

```json
{
    "more": true,
    "ss": [
        {
            "captured_at": 0,
            "key": "rF7dghtIOCO2sq7zRRmAMg",
            "mkey": "Zdns26dIV6MCevbhgzZcxw",
            "location": null,
            "starred": false,
            "user": null,
            "views": 6
        },
        {
            "captured_at": 1437785407000,
            "key": "q1W4_L_Y8u6EIyKzUfTZNg",
            "mkey": "YD9VH3xf-e1Ynic8pURtLg",
            "location": "Avenue Kennedy, NÃ®mes",
            "starred": false,
            "user": "balooval",
            "views": 4
        }
    ]
}
```

Search for sequences return a condensed format good for listing sequences.

### Scopes

Name | When
------|-----
private:read | Needed when project provided as query parameter

### HTTP Request

`GET http://a.mapillary.com/v2/search/s`

Parameter | Description
--------- | -----------
client_id | The client id of your application
start_time | Start time in EPOCH ms
end_time | End time in EPOCH ms
project | If added show only objects for that project, if not show public
hidden | Also show hidden images, only for authed user though
me | Just objects for logged in user
user | Just objects for specific user
min_lat | Minimum Latitude
max_lat | Maximum Latitude
min_lon | Minimum Longitude
max_lon | Maximum Longitude
limit | Results per page in pagination
page | Page number in pagination

### Response Parameters

Parameter | Description
--------- | -----------
more | True if there are more sequences in pagination false if not.
ss | A list of sequences in a special list format
ss[captured_at] | When the sequence was captured
ss[key] | Key of the sequence
ss[mkey] | Key of image representing sequence
ss[location] | Location where sequence was captured
ss[starred] | If sequence is starred in system
ss[user] | User thats owner of sequence
ss[views] | Number of views of sequence

## GET /search/u

```curl
curl "https://a.mapillary.com/v2/search/u?client_id=<CLIENT_ID>&match=gyl"
```

> The above command returns JSON structured like this:

```json
{
    "matches": [
        {
            "username": "gyllan"
        },
        {
            "username": "gyllen",
            "avatar": "22b939a6ac2e3920a434c0d9/profile.png"
        }
    ]
}
```

Search for usernames.

### HTTP Request

`GET http://a.mapillary.com/v2/search/u`

Parameter | Description
--------- | -----------
match | String to try to match for a username

### Response Parameters

Parameter | Description
--------- | -----------
matches[] | List of matched users
matches[username] | Matched username
matches[avatar] | If available link to avatar of matched username
