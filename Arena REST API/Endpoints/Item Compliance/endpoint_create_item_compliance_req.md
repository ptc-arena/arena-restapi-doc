# POST Item Compliance
POST /items/&lt;GUID&gt;/compliance

Creates a Compliance Requirement object with a given GUID  for an item with a given GUID.

Only one of each Compliance Requirement can be added to an Item. Any Item revision can have compliance added.

If the Compliance Requirement is added to the effective revision, it is also added to the working revisions of the Item..

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
