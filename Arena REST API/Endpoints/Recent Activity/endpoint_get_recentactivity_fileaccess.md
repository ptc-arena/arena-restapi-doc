# GET Recent Activity - File Access
/settings/recentactivities/fileaccesses

Returns an array of File Access Event objects.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all access events where results should begin. All events before the offset in the search results are ignored. The default value is 0.   |
| limit  | integer  | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| DateTimeFrom  | string  | Include all access events after this date and time  |
| DateTimeTo  | string  | Include all access events before this date and time  |

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
Get all file access events between August 1st, 2016, 11:59pm and 59 seconds and October 14th, 2016, 11:59pm and 59 seconds

GET /settings/recentactivities/fileaccesses?dateTimeFrom="2016-08-01T11:59:59Z"& dateTimeTo="2016-10-01T11:59:59Z"

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
