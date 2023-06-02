# POST Supplier Item Compliance
POST /supplieritems/&lt;GUID&gt;/compliance

Creates a Compliance Requirement object with a given GUID  for a Supplier Item with a given GUID.

Only one of each requirement can be added to a Supplier Item.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
