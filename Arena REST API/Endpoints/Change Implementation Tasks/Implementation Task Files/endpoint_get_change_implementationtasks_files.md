# GET Change Implementation Task Files


/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/files

Retrieves the files associated with a change implementation task. Implementation Task Management must be enabled within the specific change category.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
