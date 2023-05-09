# GET Outbound-Event Integrations


/outboundevents/&lt;guid&gt;

Returns a specific outbound event integration  matching the given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
