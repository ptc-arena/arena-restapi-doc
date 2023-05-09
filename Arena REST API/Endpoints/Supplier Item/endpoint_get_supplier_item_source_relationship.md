# GET Supplier Item Source Relationship


/supplieritems/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

Returns a  single  objects for a supplier item with a given GUID.

The source relationship GUID in the response is identical to the source relationship GUID for GET items/&lt;GUID&gt;/sourcing.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all source relationships where results should begin. All relationships before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400. |
| item.status | number | Specifies the revision types of items that can be included in returned results. The possible values are 0 \(working\), 1 \(effective\), 2 \(superseded\) |

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
Get a specific source relationships for a specific supplier item



/supplieritems/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

```
{
    "activeProduction": false,
    "activePrototype": true,
    "amlRank": null,
    "amlSplit": null,
    "approved": true,
    "guid": "VDXGZCXOBEWDWFGK9D4A",
    "item": {
        "guid": "7P9SBO90NQ9H0ISBNGAO",
        "name": "Resistor, 2M Ohm, 1/16W, 5%, 0603, SMD",
        "number": "180-00011",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "status": 1,
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/VDXGLBCCLSBSBQMM0UZ1",
            "app": "https://app.bom.com/VDXGLBCCLSBSBQMM0UZ1"
        } 
    },
    "makeItem": false,
    "mfrItem": {
        "guid": "5N7Q9M7YLO7CVESUDFBC",
        "number": "ERJ3GSYJ205V",
        "supplier": {
            "guid": "6O8RAN8ZMP8EXGRSZTP4",
            "name": "Matsushita"
        }
    },
    "notes": null,
    "vendorItem": {
        "guid": "3L5O7K5WJM5ATCQSBD9A",
        "number": "ERJ3GSYJ205V",
        "supplier": {
            "guid": "3L5O7K5WJM5BUDOPWQM5",
            "name": "Avnet"
        }
    },
    "vendorItemConversionFactor": 1
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
