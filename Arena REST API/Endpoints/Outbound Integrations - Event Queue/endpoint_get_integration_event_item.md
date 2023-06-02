# GET Event Item
Returns an Item from an integration event with a given GUID.

/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID/items/&lt;GUID&gt;

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get an Item from an integration event.

GET /outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "effectiveItemRevision": {
        "guid": "N5P8R4PG36PXGY8R3VWP",
        "name": "Resistor, 47 Ohm, 1/10W, 5%, 0603, SMD",
        "number": "180-00009",
        "revisionNumber": "A",
        "lifecyclePhase": {
            "name": "In Production",
            "stage": "PRODUCTION",
            "guid": "DVFYHUF6TWEH0J2L4EYV"
        },
        "modifiedSpecs": false,
        "modifiedBom": false,
        "modifiedSourcing": false,
        "modifiedFiles": false
    },
    "guid": "R9TCV8TK7ALQ9SBMD74N",
    "reconciled": true,
    "reconciledDateTime": "2020-03-16T01:40:30Z",
    "reconciledUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "supersededItemRevision": {
        "guid": "8QATCPA1ORAI1JTCOHK9",
        "number": "180-00009",
        "revisionNumber": "A",
        "lifecyclePhase": {
            "name": "In Production",
            "stage": "PRODUCTION",
            "guid": "DVFYHUF6TWEH0J2L4EYV"
        }
    }
}
```
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
