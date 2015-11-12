
# Vector Tiles

> MAPILLARY VECTOR TILE LAYERS



```
{
    "geometry": {
        "type": "LineString",
        "coordinates": [
            [
                13.038319945335386,
                55.734078661240154
            ],
            [
                13.038319945335386,
                55.73408772229796
            ],
            [
                13.038454055786133,
                55.734117925808796
            ],
            [
                13.040154576301575,
                55.734468284826406
            ],
            [
                13.04026186466217,
                55.734335390396815
            ],
            [
                13.040202856063843,
                55.73421155654382
            ],
            [
                13.040181398391724,
                55.73413604790405
            ],
            [
                13.040170669555664,
                55.73406053911823
            ]
        ]
    },
    "type": "Feature",
    "properties": {
        "username": "jesolem",
        "layer": "mapillary-sequences",
        "keys": "[\"nngnUoa9JR8q6no_RSn4Vg\", \"tU2JRf2oPQA5oTIfNmuG3Q\", \"W0KJ9IOAQoTeJmOZ9jaRHA\", \"4VCz6H7b5YFXWfarAJfhwA\", \"Pl4G2m_NFVxlQkvk_UECSA\", \"CtdZ-CDIBP8ebLqlyVasYQ\", \"jrnQ5mMtNcv6-1dVcELl7g\", \"ZxMXaXLbcjPtz6KN-rzcJg\"]",
        "cas": "[63.77213, 60.03442, 59.99939, 64.32697, 68.62, 73.33667, 74.14969, 72.56522]",
        "key": "xbWOXMuSU9IK_7nzilUq3Q",
        "captured_at": "1401121244000"
    }
}
```

>


You can access Mapillary data through vector tiles. We are using the [Mapbox vector tile format](https://github.com/mapbox/vector-tile-spec) that uses protocol buffers to store the data efficiently.

The data tiles have layers that you can interact with, for example to do hover animations and show basic information.

The tile URL pattern is:

`https://d2munx5tg0hw47.cloudfront.net/tiles/{z}/{x}/{y}.mapbox`

### Tile Content

The vector tiles contain Mapillary sequences as a list of LineString objects, example to the right.

The properties are:

Property | Description
----------------|-----| -----------
username | The user who took the sequence
layer | The name of the layer
keys | Image keys for the images in the sequence
cas | Compass angles of the images in the sequence (in degrees)
key | Sequence key for the sequence
captured_at | Time image was captured in EPOCH ms
