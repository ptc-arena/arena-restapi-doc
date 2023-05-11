# GET Recent Activity - Report Runs


/settings/recentactivities/reportruns

Returns an array of  objects.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all report runs where results should begin. All report runs before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| DateTimeFrom<br> | string<br> | Include all report runs after this date and time<br> |
| DateTimeTo<br> | string<br> | Include all report runs before this date and time<br> |

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
Get all report run events between August 1st, 2016, 11:59pm and 59 seconds and October 14th, 2016, 11:59pm and 59 seconds



GET /settings/recentactivities/reportruns?dateTimeFrom="2016\-08\-01T11:59:59Z"& dateTimeTo="2016\-10\-01T11:59:59Z"

```
{  
   "count":325,
   "results":[  
      {  
         "dateTime":"2012-07-16T23:12:52Z",
         "description":"single-source items",
         "numberOfObjects":214,
         "report":{  
            "guid":"ASCV0QRR07Q7Q511F7V0",
            "title":"Change Report",
            "type":"Changes: Lifecycle History",
            "visibility":"SHARED"
         },
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
