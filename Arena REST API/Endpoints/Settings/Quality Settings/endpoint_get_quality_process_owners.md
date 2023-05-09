# GET Quality Process Owners


/settings/qualityprocesses/owners

This returns all Quality Process Owners for a workspace.

When creating a Quality Process, if no default owner is specified for the template, you must include the GUID of an eligible owner named in this list. Otherwise, the Create Quality Process endpoint will return an error.

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
Get all Quality Process Owners in the workspace



GET /settings/qualityprocesses/owners

```
{  
   "count":17,
   "results":[  
      {  
         "fullName":"James Deckard",
         "emailAddress":"jdeckard@everyroadgps.com",
         "guid":"BJ4T3W9KW9TEWUKEFLLN"
      },
      {  
         "fullName":"Heidi Walker",
         "emailAddress":"hwalker@everyroadgps.com",
         "guid":"BJ4T3W9KW9TEWUKEFLLN"
      },
      {  
         "fullName":"Toshiro Makamuri",
         "emailAddress":"tmakamuri@everyroadgps.com",
         "guid":"BJ4T3W9KW9TEWUKEFLLN"
      },
      ...
   ]
}
```
