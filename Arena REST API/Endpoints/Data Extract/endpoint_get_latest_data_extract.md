# GET Data Extract Latest


/extracts/&lt;GUID&gt;/runs/latestCompleted

Returns a single  object \(but not the extract run content\) for the most recently completed Extract.

You can choose to include run file association information in the response. For example:



GET &lt;url&gt;/extracts/&lt;GUID&gt;/runs/latestCompleted?view=withFiles

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| view | string | This includes run file association information in the response. The only value avaialble is withFiles. |

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
