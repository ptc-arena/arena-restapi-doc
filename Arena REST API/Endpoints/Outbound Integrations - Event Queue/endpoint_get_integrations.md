# GET Integrations


/outboundintegrations/&lt;guid&gt;

Returns a specific outbound integrations object matching the given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get a specific outbound integration.



GET /outboundintegrations/&lt;GUID&gt;

```
{
    "guid": "5N7Q9M7YLOZ6P8RATFCH",
    "name": "ERP Integration",
    "enabled": true,
    "status": "UP_TO_DATE",
    "type": "OUTBOUND_MANAGED",
    "transferType": "ITEM_REVISION",
    "creator": {
        "email": "dcoronel@arenasolutions.com",
        "fullName": "Dennis Coronel",
        "guid": "FXH0JWH8VYFYH0J25014"
    },
    "creationDateTime": "2020-03-10T22:21:31Z",
    "modifyUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "modifyDateTime": "2020-03-10T23:35:29Z"
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
