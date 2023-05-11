# POST Item Compliance


POST /items/&lt;GUID&gt;/compliance

Creates a  object with a given GUID  for an item with a given GUID.

Only one of each Compliance Requirement can be added to an Item. Any Item revision can have compliance added.

If the Compliance Requirement is added to the effective revision, it is also added to the working revisions of the Item..

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "evidenceType":"AML_AND_FILES",
   "mark":"RoHS stamp",
   "rationale":"All off-the-shelf manufacturer parts qualified under this Item Number have been verified to meet the RoHS requirement.",
   "requirement": { "guid": "5N7QVLMMV2KK3M4ZHAO8"},
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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Apply a compliance requirement to an Item



POST /items/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{  
   "evidenceType":"AML_AND_FILES",
   "guid":"9RBUZPQQZ6OO7QV0DS6B",
   "lastModifiedBy":{  
      "email":"jparker@everyroadgps.com",
      "fullName":"John Parker"
   },
   "lastModifiedDateTime":"2020-09-23T18:12:12Z",
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
