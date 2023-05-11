# GET Item Compliance Requirement


GET /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Returns a  object with a given GUID for an item with a given GUID.

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
Get a single item compliance requirement



GET /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{  
   "evidenceType":"AML_AND_FILES",
   "guid":"9RBUZPQQZ6OO7QV0DS6B",
   "lastModifiedBy":{  
      "email":"jparker@everyroadgps.com",
      "fullName":"John Parker"
   },
   "lastModifiedDateTime":"2016-09-23T18:12:12Z",
   "mark":"RoHS stamp",
   "propagated":false,
   "rationale":"All off-the-shelf manufacturer parts qualified under this Item Number have been verified to meet the RoHS requirement.",
   "requirement":{  
      "guid":"5N7QVLMMV2KK3M4ZHAO8",
      "name":"2011/65/EU RoHS"
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
