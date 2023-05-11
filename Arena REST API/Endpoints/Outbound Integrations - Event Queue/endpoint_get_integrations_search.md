# GET Integrations (Search)


/outboundintegrations

Returns a collection of outbound integrations objects matching the given search criteria.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| enabled<br> | string<br> | Indicates if an Integration is enabled. The value is true if the integration is enabled. The value is false if the integration is disabled.<br> |
| name<br> | string<br> | The name of the outbound integration.<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results.

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
Get all outbound integrations



GET /outboundintegrations

```
{
    "count": 3,
    "results": [
        {
            "guid": "5N7Q9M7YLOZ6P8RATFCH",
            "name": "ERP Integration",
            "enable": true,
            "status": "OUTBOUND_MANAGED",
            "type": "UP_TO_DATE",
            "transferType": "ITEM_REVISION"
        },
        {
            "guid": "7P9SBO90NQ18RATCVHE1",
            "name": "XYZ Integration",
            "enable": true,
            "status": "OUTBOUND_MANAGED",
            "type": "UP_TO_DATE",
            "transferType": "ITEM_REVISION"
        },
        {
            "guid": "8QATCPA1OR29SBUDWIF4",
            "name": "Deactivated Integration",
            "enable": false,
            "status": "OUTBOUND_MANAGED",
            "type": "DISABLED",
            "transferType": "ITEM_REVISION"
        }
    ]
}
```
Get outbound integrations that are enabled



GET &lt;url&gt;/outboundintegrations?enabled=true

```
{
    "count": 2,
    "results": [
        {
            "guid": "5N7Q9M7YLOZ6P8RATFCH",
            "name": "ERP Integration",
            "enable": true,
            "status": "OUTBOUND_MANAGED",
            "type": "UP_TO_DATE",
            "transferType": "ITEM_REVISION"
        },
        {
            "guid": "7P9SBO90NQ18RATCVHE1",
            "name": "XYZ Integration",
            "enable": true,
            "status": "OUTBOUND_MANAGED",
            "type": "UP_TO_DATE",
            "transferType": "ITEM_REVISION"
        }
    ]
}
```
Request with an invalid search attribute.

GET /outboundintegrations?transferType=Item Revision

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3003,
         "message":"The value for the attribute \"trasnferType\" is not valid."
      }
   ]
}
```
