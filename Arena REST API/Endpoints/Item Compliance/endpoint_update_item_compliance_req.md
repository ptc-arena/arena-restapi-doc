# PUT Item Compliance Update


PUT /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Updates a  object with a given GUID  for an item with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "mark":"blue checkmark on packaging",
   "rationale":"evidence provided by files attached to item",
   "evidenceType":"DIRECT_FILES",
   "status":"UNKNOWN"
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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Update a compliance requirement for an Item



PUT /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{  
   "evidenceType":"DIRECT_FILES",
   "guid":"6O8RAIPBRZHH0J2J0ZY0",
   "lastModifiedBy":{  
      "fullName":"Heidi Walker"
   },
   "lastModifiedDateTime":"2015-08-01T00:47:41Z",
   "mark":"blue checkmark on packaging",
   "propagated":true,
   "rationale":"evidence provided by files attached to item",
   "requirement":{  
      "guid":"3L5O7FM8OWEEXGZHNPBN",
      "name":"2011/65/EU RoHS"
   },
   "status":"UNKNOWN"
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
