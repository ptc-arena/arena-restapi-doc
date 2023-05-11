# GET Supplier Item Compliance


/supplieritems/&lt;GUID&gt;/compliance

Returns all  objects for a supplier item with a given GUID.

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
