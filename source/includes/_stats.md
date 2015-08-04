# Stats /stats

## GET /stats/im

```curl
curl "https://a.mapillary.com/v2/stats/im?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "images": 27450593,
    "distance": 703360611
}
```

Stats about images in Mapillary system

### HTTP Request

`GET http://a.mapillary.com/v2/stats/im`

### Response Parameters

Parameter | Description
--------- | -----------
images | Total number of images on Mapillary
distance | Total meters mapped on Mapillary

## GET /stats/im/toplist

```curl
curl "https://a.mapillary.com/v2/stats/toplist?client_id=<CLIENT_ID>&cname=sweden"
```

> The above command returns JSON structured like this:

```json
{
  "toplist": [
    {
      "list": [
        {
          "username": "jesolem",
          "count": 938
        },
        {
          "username": "mthagaard",
          "count": 334
        }
      ],
      "week": "41"
    }
  ],
  "total": [
    {
      "username": "vicroads",
      "count": 3276096
    },
    {
      "username": "cogg",
      "count": 2119347
    }
  ],
  "total_count": 27496346
}
```

Top lists stats for Mapillary.

### HTTP Request

`GET http://a.mapillary.com/v2/stats/toplist`

Parameter | Description
--------- | -----------
cname | Name of country for stats (optional if not added whole world is assumed)
limit | Number of users in every list (default 10, optional)

### Response Parameters

Parameter | Description
--------- | -----------
toplist | List of toplists per week
toplist[list] | The actual list
toplist[list][username] | Username in list
toplist[list][count] | Count of images in that week for user
total | The total toplist over all weeks
total[username] | Username in list
total[count] | Count of images in total for user
total_count | Total number of images in selection
