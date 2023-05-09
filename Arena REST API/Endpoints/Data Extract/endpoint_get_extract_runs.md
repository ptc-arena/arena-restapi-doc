# GET Extract Runs Search


/extracts/&lt;GUID&gt;/runs

Returns  objects  for an extract with a given GUID. 
Appending a run GUID returns the run with that GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all runs where results should begin. All runs before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. By default the maximum number of runs is 20. Can return up 400 runs. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| status | string | status of the Extract. Values can be InProcess, Completed, Failed, or Aborted. |
| scheduledDateTimeFrom | string | Include runs scheduled after this date and time |
| scheduledDateTimeTo | string | Include runs scheduled before this date and time |
| runDateTimeFrom | string | Include runs executed after this date and time |
| runDateTimeTo | string | Include runs executed before this date and time |
| completionDateTimeFrom | string | Include runs completed after this date and time |
| completionDateTimeTo | string | Include runs completed before this date and time |
| downloadDateTimeFrom | string | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)  |
| downloadDateTimeTo | string | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)  |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

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
Get extracts which ran between  and  \(inclusive\).



GET /extracts/&lt;GUID&gt;/runs?runDateTimeFrom="2015\-04\-19T23:59:59Z"&runDateTo="2015\-09\-30T23:59:59Z"

```
{  
   "count":5,
   "results":[  
      {  
         "completionDate":"2015-04-20T20:14:21Z",
         "completionDateTime":"2015-04-20T20:14:21Z",
         "creator":{  
            "fullName":"Extract Extraction"
         },
         "guid":"BTDWA7BDO5OFYH0J2L22",
         "runDateTime":"2015-04-20T20:14:15Z",
         "scheduledDateTime":null,
         "status":"COMPLETED"
      },
      {  
         "completionDate":"2015-07-08T21:21:48Z",
         "completionDateTime":"2015-07-08T21:21:48Z",
         "creator":{  
            "fullName":"Extract Extraction"
         },
         "guid":"WEYHVSWY9Q90J2L4N6EP",
         "runDateTime":"2015-07-08T21:21:45Z",
         "scheduledDateTime":null,
         "status":"COMPLETED"
      },
      {  
         "completionDate":"2015-07-28T21:24:32Z",
         "completionDateTime":"2015-07-28T21:24:32Z",
         "creator":{  
            "fullName":"Extract Extraction"
         },
         "guid":"P7RAOLPR2J2TCVEXGZ48",
         "runDateTime":"2015-07-28T21:24:29Z",
         "scheduledDateTime":null,
         "status":"COMPLETED"
      },
      {  
         "completionDate":"2015-09-29T17:50:52Z",
         "completionDateTime":"2015-09-29T17:50:52Z",
         "creator":{  
            "fullName":"Extract Extraction"
         },
         "guid":"1J3M0X13EVE5O7Q9SB70",
         "runDateTime":"2015-09-29T17:50:47Z",
         "scheduledDateTime":null,
         "status":"COMPLETED"
      },
      {  
         "completionDate":"2015-09-29T17:54:45Z",
         "completionDateTime":"2015-09-29T17:54:45Z",
         "creator":{  
            "fullName":"Extract Extraction"
         },
         "guid":"2K4N1Y24FWF6P8RATC8T",
         "runDateTime":"2015-09-29T17:54:43Z",
         "scheduledDateTime":null,
         "status":"COMPLETED"
      }
   ]
}
```
Get a specific run



GET /extracts/&lt;GUID&gt;/runs/BTDWA7BDO5OFYH0J2L22

```
{  
   "completionDate":"2015-04-20T20:14:21Z",
   "completionDateTime":"2015-04-20T20:14:21Z",
   "creator":{  
      "fullName":"Extract Extraction"
   },
   "guid":"BTDWA7BDO5OFYH0J2L22",
   "runDateTime":"2015-04-20T20:14:15Z",
   "scheduledDateTime":null,
   "status":"COMPLETED"
}
```
An error is returned if:

* the GUID is not valid.

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
* An error is thrown by the file server

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3017,
         "message":"The file with guid \"7P60AQ9P8RAS7F6J\" cannot be downloaded at this time."
      }
   ]
}
```
* \*If the file server is inaccessible, it may return a 400 status with no message.

