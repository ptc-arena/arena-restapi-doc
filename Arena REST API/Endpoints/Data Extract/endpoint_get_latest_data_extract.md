# GET Data Extract Latest
/extracts/&lt;GUID&gt;/runs/latestCompleted

Returns a single Extract object \(but not the extract run content\) for the most recently completed Extract.

You can choose to include run file association information in the response. For example:

GET &lt;url&gt;/extracts/&lt;GUID&gt;/runs/latestCompleted?view=withFiles

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| view<br> | string<br> | This includes run file association information in the response. The only value avaialble is withFiles.<br> |

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

## Sample Response Body
Get the latest data extract, including file information

GET /extracts/&lt;GUID&gt;/runs/latestCompleted?view=withFiles

```
{  
   "completionDate":"2015-09-29T17:54:45Z",
   "completionDateTime":"2015-09-29T17:54:45Z",
   "creator":{  
      "fullName":"Extract Extraction"
   },
   "files":[  
      {  
         "downloadDateTime":"2015-09-29T17:55:20Z",
         "guid":"1J3M0X13EVE4N6P66T44"
      }
   ],
   "guid":"2K4N1Y24FWF6P8RATC8T",
   "runDateTime":"2015-09-29T17:54:43Z",
   "scheduledDateTime":null,
   "status":"COMPLETED"
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
