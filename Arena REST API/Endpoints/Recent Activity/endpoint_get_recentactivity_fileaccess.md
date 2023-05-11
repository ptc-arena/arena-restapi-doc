# GET Recent Activity - File Access


/settings/recentactivities/fileaccesses

Returns an array of  objects.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all access events where results should begin. All events before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| DateTimeFrom<br> | string<br> | Include all access events after this date and time<br> |
| DateTimeTo<br> | string<br> | Include all access events before this date and time<br> |

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
Get all file access events between August 1st, 2016, 11:59pm and 59 seconds and October 14th, 2016, 11:59pm and 59 seconds



GET /settings/recentactivities/fileaccesses?dateTimeFrom="2016\-08\-01T11:59:59Z"& dateTimeTo="2016\-10\-01T11:59:59Z"

```
{  
   "count":325,
   "results":[  
      {  
         "activity":"New Edition created",
         "comments":"Editing for grammar and typos",
         "dateTime":"2016-09-14T21:37:09Z",
         "file":{  
            "edition":"3",
            "guid":"8QAT748AL2LVEXDVFJKI",
            "name":"assy_instr.docx",
            "title":"Assy Instructions",
            "markup":{  
               "guid":"UCWFKABBKRAGZINDEEM1",
               "title":"Assy Instructions",
               "name":"assy_instr.docx"
            },
            "user":{  
               "email":"hwalker@everyroadgps.com",
               "guid":"7P9S6379K1KUDW8FUIY9",
               "fullName":"Heidi Walker"
            }
         }
      },
      …
   ]
}
```
