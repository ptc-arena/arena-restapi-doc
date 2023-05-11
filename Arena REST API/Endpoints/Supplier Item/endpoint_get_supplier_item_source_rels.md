# GET Supplier Item Source Relationships


/supplieritems/&lt;GUID&gt;/sourcing

Returns a collection of  objects for a supplier item with a given GUID.

The source relationship GUID in the responses is identical to the source relationship GUID for GET items/&lt;GUID&gt;/sourcing.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all source relationships where results should begin. All relationships before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.<br> |
| item.status<br> | number<br> | Specifies the revision types of items that can be included in returned results. The possible values are 0 \(working\), 1 \(effective\), 2 \(superseded\)<br> |

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
Get source relationships for a supplier item



/supplieritems/&lt;GUID&gt;/sourcing

```
{  
   "count":2,
   "results":[  
      {  
         "activeProduction":false,
         "activePrototype":false,
         "amlRank":null,
         "amlSplit":null,
         "approved":true,
         "guid": "VDXGZCXOBEWDWFGK9D4A",
         "item":{  
            "guid":"5N7QVLMMV2L2L0WWA3PY",
            "name": "Capacitor, Ceramic Chip, 0.01uF, 0603",
            "number": "120-00005",
            "revisionNumber": "A",
            "revisionStatus": "WORKING",
            "status": 0,
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/5N7QVLMMV2L2L0WWA3PY",
                "app": "https://app.bom.com/5N7QVLMMV2L2L0WWA3PY"
            }
         },
         "makeItem":false,
         "mfrItem":{  
            "guid":"I0K38YZZ8FY3M55VE92O"
         },
         "notes":"Reel",
         "vendorItem":{  
            "guid":"HZJ27XYY7EX2L44UD816"
         },
         "vendorItemConversionFactor":1
      },
      {  
         "activeProduction":false,
         "activePrototype":false,
         "amlRank":null,
         "amlSplit":null,
         "approved":true,
         "guid": "VDXGZCXOBEWDWFGK9D4A",
         "item":{  
            "guid":"VDXGLBCCLSBSBQMM0UZ1",
            "name": "Capacitor, Ceramic Chip, 0.01uF, 0603",
            "number": "120-00005",
            "revisionNumber": "A",
            "revisionStatus": "EFFEC|TIVE",
            "status": 1,
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/VDXGLBCCLSBSBQMM0UZ1",
                "app": "https://app.bom.com/VDXGLBCCLSBSBQMM0UZ1"
            }     
         },
         "makeItem":false,
         "mfrItem":{  
            "guid":"I0K38YZZ8FY3M55VE92O"
         },
         "notes":"Reel",
         "vendorItem":{  
            "guid":"HZJ27XYY7EX2L44UD816"
         },
         "vendorItemConversionFactor":1
      }
   ]
}

```
Request with bad GUID:

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"0I2LQGHHQXGXGVRR5XND\" is not valid."
      }
   ]
}
```
