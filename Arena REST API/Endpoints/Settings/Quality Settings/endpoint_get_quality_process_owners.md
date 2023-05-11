# GET Quality Process Owners


/settings/qualityprocesses/owners

This returns all Quality Process Owners for a workspace.

When creating a Quality Process, if no default owner is specified for the template, you must include the GUID of an eligible owner named in this list. Otherwise, the Create Quality Process endpoint will return an error.

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
