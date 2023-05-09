# GET Recent Activity - User Access


/settings/recentactivities/useraccesses

Returns an array of  objects.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all logins where results should begin. All logins before the offset in the search results are ignored. The default value is 0.  |
| limit | integer | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| DateTimeFrom | string | Include all logins after this date and time |
| DateTimeTo | string | Include all logins before this date and time |

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

## Sample Responses
Get all user logins on January 1st 2017 \(no offset, 50 result limit\)



GET /settings/recentactivities/useraccesses?offset=0&limit=50&dateTimeFrom= 2017\-01\-01T00:00:00Z&dateTimeFrom=2017\-01\-01T23:59:59Z

```
{  
   "count":50,
   "results":[  
      {  
         "connectedThrough":"ARENA_PLM",
         "domain":"everyroadgps.com",
         "duration":265,
         "loginDateTime":"2016-09-03T22:57:02Z",
         "logoutDateTime":"2016-09-03T22:59:12Z",
         "originatingIp":"71.94.69.211",
         "user":{  
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"7P9S6379K1KUDW8FUIY9"
         }
      },
      …
   ]
}
```
