# GET Change Implementation Task Files
/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/files

Retrieves the files associated with a change implementation task. Implementation Task Management must be enabled within the specific change category.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all files of an implementation task of a specific change.

GET /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/files

```
{
    "count": 20,
    "results": [
        {
           "guid": "I0K3HEIKVCT8RATCV2DU",
           "file": {
               "guid": "GYI1FCGITAT9SB0IJX9M",
               "number": "FILE-046012",
               "edition": "1",
               "name": "implementation plan.pdf",
               "storageMethodName": "FILE",
               "title": "Implementation Plan"
        },
        {
           "guid": "XFZI1EZQDGY9SBUCQ8JJ",
           "file": {
               "guid": "M4O7Q3OF25OK3M5OHUQ2",
               "number": "FILE-046017",
               "edition": "1",
               "location": "http://www.somewhere.com",  # for WEB
               "storageMethodName": "WEB",
               "title": "Implementation Plan"
        },
        ...
    ]
}
```
Request with invalid GUID

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
