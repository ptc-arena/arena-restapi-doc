# GET Outbound-Event Integrations
/outboundevents/&lt;guid&gt;

Returns a specific outbound event integration  matching the given GUID.

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
Get a specific outbound event integration.

GET /outboundevents/&lt;GUID&gt;

```
{
    "creationDateTime": "2021-07-20T23:32:02Z",
    "creator": {
        "email": "cstone@everyroadgps.com",
        "fullName": "Craig Stone",
        "guid": "FXH0JWH8VYFYH0J25014"
    },
    "enabled": true,
    "guid": "2K4N6J4VILWUDWFYH3YT",
    "lastModifiedDateTime": "2021-08-06T21:41:31Z",
    "modifyUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "name": "EveryHome Outbound Event Integration",
    "status": "NEEDS_ATTENTION"
}
```
Request with an invalid GUID.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"5N7Q9M7YL0Z6P8RATFCI\" is not valid."
      }
   ]
}
```
