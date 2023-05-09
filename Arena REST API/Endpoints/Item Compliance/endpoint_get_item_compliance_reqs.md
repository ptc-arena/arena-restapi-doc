# GET Item Compliance Requirements


/items/&lt;GUID&gt;/compliance

Returns all  objects for an item with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
Get all Compliance Requirements applied to an item



GET /items/GUID/compliance

```
{  
   "count":2,
   "results":[  
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
      },
      {  
         "evidenceType":"DIRECT_FILES",
         "guid":"9RBUZPQQZ6OO7QV0DS6B",
         "lastModifiedBy":{  
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "lastModifiedDateTime":"2016-09-23T18:12:12Z",
         "mark":"none",
         "propagated":false,
         "rationale":"First article verified by Everyroad",
         "requirement":{  
            "guid":"5N7QVLMMV2KK3M4ZHAO8",
            "name":"First Article Inspection"
         },
         "status":"COMPLIANT"
      }
   ]
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
