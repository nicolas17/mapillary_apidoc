# Comments /cm

> /v2/cm

Manage comments.

## GET /cm/:key

> /v2/cm/:key

```curl
curl "https://a.mapillary.com/v2/cm/v-fa0oYnRnpy6vzbmGRTCQ?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "comment": "Next time you got to catch the whole way down.",
    "created_at": 1438038345237,
    "key": "v-fa0oYnRnpy6vzbmGRTCQ",
    "mkey": "4fjj5tH4yBpp6m6iItlc-w",
    "user": "gyllen"
}
```

Retrieve information about a specific comment.

### Scopes

Name | When
-----|-----
private:read | Needed when accessing comments made on private images

### HTTP Request

`GET https://a.mapillary.com/v2/cm/:key`

Parameter | Description
--------- | -----------
key | Key of the comment

### Response Parameters

Parameter | Description
--------- | -----------
client_id | The client id belonging to your application
comment | The actual comment
created_at | Time comment was created in EPOCH ms
key | Key of the comment
mkey | Key of corresponding image
user | User making the comment

## DELETE /cm/:key

> /v2/cm/:key

```curl
curl -XDELETE "https://a.mapillary.com/v2/cm/v-fa0oYnRnpy6vzbmGRTCQ?client_id=<CLIENT_ID>"
```

> The above command returns JSON structured like this:

```json
{
    "code": "ok",
    "message": "request performed",
    "status": 200
}
```

Remove a comment.

### Scopes

Name | When
-----|-----
public:write | When removing a user comment on a public image
private:write | When removing a user comment on a private image

### HTTP Request

`DELETE https://a.mapillary.com/v2/cm/:key`

Parameter | Description
--------- | -----------
key | Key of the comment
