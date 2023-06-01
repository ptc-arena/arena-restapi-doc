# GET Supplier Item Compliance Requirement
GET /supplieritems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Returns a Compliance Requirement with a given GUID  for a supplier item with a given GUID.

## Request Headers

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Headers

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Successful Response Body

| Name<br> | Description<br> |
|  --- |  --- | 
| result<br> | a single compliance requirement<br> |

## Unsuccessful Response Body

| Name<br> | Description<br> |
|  --- |  --- | 
| status<br> | HTTP status<br> |
| errors<br> | Collection of errors, including an Arena error code and message for each.<br> |

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
