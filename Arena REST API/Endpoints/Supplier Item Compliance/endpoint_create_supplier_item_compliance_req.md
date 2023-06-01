# POST Supplier Item Compliance
POST /supplieritems/&lt;GUID&gt;/compliance

Creates a Compliance Requirement object with a given GUID  for a Supplier Item with a given GUID.

Only one of each requirement can be added to a Supplier Item.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "requirement":{  
      "guid":"HZJ2LYJAX0IEXGYHQ7KA",
   },
   "evidenceType":"DIRECT_FILES",
   "mark":"the compliance mark",
   "rationale":"This Supplier Item has been verified to meet the RoHS requirement.",
   "status":"COMPLIANT"
}
```
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
Create a compliance requirement for a Supplier Item

POST /items/&lt;GUID&gt;/compliance

```
{  
   "evidenceType":"DIRECT_FILES",
   "guid":"J1L4N0LCZ2KGZISABJ8Q",
   "lastModifiedBy":{  
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "lastModifiedDateTime":"2020-11-04T19:28:23Z",
   "mark":"the compliance mark",
   "rationale":"This Supplier Item has been verified to meet the RoHS requirement.",
   "requirement":{  
      "guid":"HZJ2LYJAX0IEXGYHQ7KA",
      "name":"2002/95/EC RoHS (Sample)"
   },
   "status":"COMPLIANT"
}
```
Request with invalid evidence type or status

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3082,
         "message":"Invalid evidence type."
      }
   ]
}
```
