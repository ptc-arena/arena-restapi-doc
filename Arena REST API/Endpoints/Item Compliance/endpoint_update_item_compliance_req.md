# PUT Item Compliance Update


PUT /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Updates a  object with a given GUID  for an item with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
