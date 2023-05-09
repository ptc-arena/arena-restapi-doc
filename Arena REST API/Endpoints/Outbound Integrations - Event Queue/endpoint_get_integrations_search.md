# GET Integrations (Search)


/outboundintegrations

Returns a collection of outbound integrations objects matching the given search criteria.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| enabled | string | Indicates if an Integration is enabled. The value is true if the integration is enabled. The value is false if the integration is disabled. |
| name | string | The name of the outbound integration. |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results.

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
