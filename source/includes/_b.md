# Blurs /b

> /v2/b

Manage blurs.

## GET /b/:key

> /v2/b/:key

```curl
curl "https://a.mapillary.com/v2/b/UUyAhNVPHTAdOeCgJwa4dg?client_id=<CLIENT_ID>"
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

Retrive information about a specific blur.

### Scopes

Name | When
-----|-----
private:read | Needed when accessing blurs made on private images

### HTTP Request

`GET https://a.mapillary.com/v2/b/:key`

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
key | Key of the blur

### Response Parameters

Parameter | Description
--------- | -----------
bs | List of blurs for image
bs[type] | Describes type of blur, face = face detected, license = license plate detected, user = user defined blur
bs[rect] | Placement of blur as a rectangle, [SouthWest, NorthEast] -> [[x,y],[x,y]]
user | User who decided the blur, if null its mapillary default
applied | True if applied false if not


## POST /cm/:key

> /v2/cm/:key

```curl
curl -XPOST "https://a.mapillary.com/v2/b/UUyAhNVPHTAdOeCgJwa4dg?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Approve a none approved blur.

### Scopes

Name | When
-----|-----
mapillary:admin | Always

### HTTP Request

`POST https://a.mapillary.com/v2/b/:key`

Parameter | Description
--------- | -----------
key | Key of the comment

## DELETE /cm/:key

> /v2/cm/:key

```curl
curl -XPOST "https://a.mapillary.com/v2/b/UUyAhNVPHTAdOeCgJwa4dg?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Reject a none approved blur.

### Scopes

Name | When
-----|-----
mapillary:admin | Always

### HTTP Request

`DELETE https://a.mapillary.com/v2/b/:key`

Parameter | Description
--------- | -----------
key | Key of the comment
