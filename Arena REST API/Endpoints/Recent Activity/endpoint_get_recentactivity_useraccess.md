# GET Recent Activity - User Access
/settings/recentactivities/useraccesses

Returns an array of Login objects.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all logins where results should begin. All logins before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| DateTimeFrom<br> | string<br> | Include all logins after this date and time<br> |
| DateTimeTo<br> | string<br> | Include all logins before this date and time<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
Get all user logins on January 1st 2017 \(no offset, 50 result limit\)

GET /settings/recentactivities/useraccesses?offset=0&limit=50&dateTimeFrom= 2017-01-01T00:00:00Z&dateTimeFrom=2017-01-01T23:59:59Z

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
