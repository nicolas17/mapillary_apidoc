# Errors

## Error codes

> MAPILLARY HTTP ERROR CODES

```curl
200 OK - Everything worked as expected.
400 Bad Request - Often missing a required parameters.
401 Unauthorized - Your client_id is invalid, the oauth token is invalid, client_id and oauth token does not match.
404 Not Found - The API does not exists, the requested object does not exist.
429 Too Many Requests - You're requesting over your limit.
500 Internal Server Error - Something went wrong on Mapillarys servers.
```

>

The Mapillary API uses the following HTTP error codes:

Error Code | Meaning | Description
---------- | ------- | -----------
200 | OK | Everything worked as expected.
400 | Bad Request | Often missing a required parameters.
401 | Unauthorized | Your client_id is invalid, the oauth token is invalid, client_id and oauth token does not match.
404 | Not Found | The API does not exists, the requested object does not exist.
429 | Too Many Requests | You're requesting over your limit.
500 | Internal Server Error | Something went wrong on Mapillarys servers.

## Error messages

> MAPILLARY ERROR RETURN FORMAT

```json
{
  "code": "client_id_invalid",
  "message": "This API call needs a client_id"
}
```

>
> MAPILLARY ERROR RETURN CODES

```curl
400 parameter_missing - One or more parameters are missing
400 parameter_invalid - One or more parameters are invalid
401 client_id_differ - The provided client id differs from auth token
401 client_id_invalid - The provided client id is invalid
401 client_id_missing - This API call needs a client_id
401 user_not_authenticated - User Not Authenticated
404 not_found - Resource not found
500 mapillary_internal_server_error - Internal Error: XXX
```

>

The Mapillary API can return the following error codes.

### Response Parameters

Parameter | Description
--------- | -----------
code | The Mapillary error code
message | A short message describing the error

### Codes

HTTP Error code | Code | Description
----------------|-----| -----------
400 | parameter_missing | One or more parameters are missing
400 | parameter_invalid | One or more parameters are invalid
401 | client_id_differ | The provided client id differs from auth token
401 | client_id_invalid | The provided client id is invalid
401 | client_id_missing | This API call needs a client_id
401 | user_not_authenticated | User Not Authenticated
404 | not_found | Resource not found
500 | mapillary_internal_server_error | Internal Error: XXX
