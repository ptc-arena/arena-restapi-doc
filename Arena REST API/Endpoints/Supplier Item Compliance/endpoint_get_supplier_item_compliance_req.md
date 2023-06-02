# GET Supplier Item Compliance Requirement
GET /supplieritems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Returns a Compliance Requirement with a given GUID  for a supplier item with a given GUID.

## Request Headers

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Headers

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Successful Response Body

| Name  | Description  |
|  --- |  --- | 
| result  | a single compliance requirement  |

## Unsuccessful Response Body

| Name  | Description  |
|  --- |  --- | 
| status  | HTTP status  |
| errors  | Collection of errors, including an Arena error code and message for each.  |

## Sample Responses
Get a single supplier item compliance requirement

GET /supplieritems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{
   "evidenceType":"DIRECT_FILES",
   "guid":"XFYH0J10J2CU9P5Z",
   "lastModifiedBy":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "lastModifiedDateTime":"07/05/2011 01:42:37 PM",
   "mark":null,
   "rationale":"- This Supplier Item has been verified to meet the RoHS requirement.",
   "requirement":{
      "guid":"8QATYOPPY5NM5O61JCQW",
      "name":"2002/95/EC RoHS (Sample)"
   },
   "status":"COMPLIANT"
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
