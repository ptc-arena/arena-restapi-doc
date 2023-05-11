# GET Integration Administrators


/outboundevents/&lt;GUID&gt;/administrators

Returns all the integration administrators of a specific outbound event integration matching the given GUID.

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
Get the integration administrators of  a specific outbound events integration.



GET /outboundevents/&lt;GUID&gt;/administrators

```
{
    "count": 3,
    "results": [
        {
            "email": "rborger@everyroadgps.com",
            "fullName": "Rachael Borger",
            "guid": "VDXGZCXOBEVEXGZIRHOJ"
        },
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
