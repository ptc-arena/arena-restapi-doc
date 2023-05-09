# GET Supplier Item Compliance


/supplieritems/&lt;GUID&gt;/compliance

Returns all  objects for a supplier item with a given GUID.

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
Get all Compliance Requirements applied to a supplier item



GET /supplieritems/GUID/compliance

```
{  
   "count":1,
   "results":[  
      {  
         "evidenceType":"DIRECT_FILES",
         "guid":"XFYH0J10J2CU9P5Z",
         "lastModifiedBy":{  
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "lastModifiedDateTime":"07/05/2011 01:42:37 PM",
         "mark":"RoHS logo on packaging",
         "rationale":"Testing phase",
         "requirement":{  
            "guid":"8QATYOPPY5NM5O61JCQW",
            "name":"2002/95/EC RoHS"
         },
         "status":"UNKNOWN"
      }
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
