# GET Event Item
Returns an Item from an integration event with a given GUID.

/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID/items/&lt;GUID&gt;

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
