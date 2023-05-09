# GET Integrations


/outboundintegrations/&lt;guid&gt;

Returns a specific outbound integrations object matching the given GUID.

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
