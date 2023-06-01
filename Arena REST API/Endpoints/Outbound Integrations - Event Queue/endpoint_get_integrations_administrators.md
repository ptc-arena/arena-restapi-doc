# GET Integration Administrators
/outboundintegrations/&lt;guid&gt;/administrators

Returns all the integration administrators of a specific outbound integrations objects matching the given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

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
Get the integration administrators of  a specific outbound integration.

GET /outboundintegrations/&lt;GUID&gt;/administrators

```
{
    "count": 2,
    "results": [
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        },
        {
            "email": "ecanard@everyroadgps.com",
            "fullName": "Eleanor Canard",
            "guid": "1J3M5I3UHK1K3M5OXNUV"
        }
    ]
}
```
Request with an invalid GUID.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"5D7Q9M7YL0Z6P8RATBDS\" is not valid."
      }
   ]
}
```
