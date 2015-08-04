# Sequences /s

## GET  /s/:key

> /v2/s/:key

```curl
curl "https://a.mapillary.com/v2/s/XXhG1IuvngsFAw-zRrk6cg?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "boundary": {
        "min_lat": 58.85197745,
        "min_lon": 5.74313594,
        "max_lat": 58.85199353,
        "max_lon": 5.74316249
    },
    "captured_at": 1437142973705,
    "cas": [
        340.360486328602,
        358.657117366791
    ],
    "coords": [
        [
            5.74313594,
            58.85199353
        ],
        [
            5.74313632,
            58.85199297
        ]
    ],
    "key": "XXhG1IuvngsFAw-zRrk6cg",
    "keys": [
        "TaBv0AZF5kloqhnbyOuZHw",
        "EGJ-FwLmvspXe04vmnWfKg"
    ]
}
```

Retrive information about a specific sequence.

### Scopes

Name | When
-----|-----
private:read | Needed when accessing private sequences

### HTTP Request

`GET https://a.mapillary.com/v2/s/:key`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the sequence to get information about

### Response Parameters

Parameter | Description
--------- | -----------
boundary | Box covering the whole sequence
captured_at | When the sequence was captured
cas | List of angles
coords | List of coords for the sequence
key | Key of the sequence
keys | Array of the keys of the images in the sequence

## GET  /s/:key/geojson

> /v2/s/:key/geojson

```curl
curl "https://a.mapillary.com/v2/s/XXhG1IuvngsFAw-zRrk6cg/geojson?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "more": false,
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "LineString",
                "coordinates": [
                    [
                        5.74313594,
                        58.85199353
                    ],
                    [
                        5.74313632,
                        58.85199297
                    ]
                ],
                "bbox": [
                    5.74313594,
                    58.85197745,
                    5.74316249,
                    58.85199353
                ]
            },
            "properties": {
                "boundary": {
                    "min_lat": 58.85197745,
                    "min_lon": 5.74313594,
                    "max_lat": 58.85199353,
                    "max_lon": 5.74316249
                },
                "captured_at": 1437142973705,
                "key": "XXhG1IuvngsFAw-zRrk6cg",
                "keys": [
                    "TaBv0AZF5kloqhnbyOuZHw",
                    "EGJ-FwLmvspXe04vmnWfKg"
                ],
                "cas": [
                    340.360486328602,
                    358.657117366791
                ]
            }
        }
    ],
    "type": "FeatureCollection"
}
```

Retrive information about a specific sequence in geojson format.

### Scopes

Name | When
-----|-----
private:read | Needed when accessing private sequences

### HTTP Request

`GET https://a.mapillary.com/v2/s/:key/geojson`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the sequence to get information about

### Geojson Properties

Parameter | Description
--------- | -----------
boundary | Box covering the whole sequence
captured_at | When the sequence was captured
key | Key of the sequence
keys | Array of the keys of the images in the sequence
cas | List of angles
