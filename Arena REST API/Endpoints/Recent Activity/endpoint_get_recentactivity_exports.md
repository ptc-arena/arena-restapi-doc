# GET Recent Activity - Exports
/settings/recentactivities/exports

Returns an array of Export Event objects.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all exports where results should begin. All exports before the offset in the search results are ignored. The default value is 0.   |
| limit  | integer  | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| DateTimeFrom  | string  | Include all exports after this date and time  |
| DateTimeTo  | string  | Include all exports before this date and time  |

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
Get all exports between August 1st, 2016, 11:59pm and 59 seconds and October 14th, 2016, 11:59pm and 59 seconds

GET /settings/recentactivities/exports?dateTimeFrom="2016-08-01T11:59:59Z"& dateTimeTo="2016-10-01T11:59:59Z"

```
{  
   "count":325,
   "results":[  
      {  
         "configuration":"Item Export (Found Items)",
         "dateTime":"2007-07-10T15:37:55Z",
         "numberOfResources":384,
         "type":"Items",
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
