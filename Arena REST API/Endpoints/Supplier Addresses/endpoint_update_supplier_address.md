# PUT Supplier Profile Address Edit
/suppliers/&lt;GUID&gt;/addresses/&lt;GUID&gt;

Updates an existing specific phone numbers of a supplier with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
```
{
    "address": {
        "address1": "2222 South 48th St",
        "address2": null,
        "city": "Phoenix",
        "Country/Region": "United States",
        "label": "Main",
        "postalCode": "85034",
        "province": null,
        "state": "ARIZONA"
    },
    "primary": false
}  
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Updates a specific address for a supplier.

/suppliers/&lt;GUID&gt;/addresses/&lt;GUID&gt;

```
{
    "address": {
        "address1": "2222 South 48th St",
        "address2": null,
        "city": "Phoenix",
        "Country/Region": "United States",
        "guid": "ZH1JUUK1WRASBUDQT110",
        "label": "Main",
        "postalCode": "85034",
        "province": null,
        "state": "ARIZONA"
    },
    "primary": false
}    
```
Request with bad GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3011,
            "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
        }
    ]
}
```
