# POST Change Implementation Task File


/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/files

Adds a specific, already existing in the workspace, File to a specific implementation task. Implementation Task Management must be enabled to execute this endpoint. Not supported for Canceled or Completed Changes.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
Adds an existing file to an existing implementation task.

```
{
    "file": {
        "guid": "GYI1FCGITAT9SB0IJX9M"
    }
}
```
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
Adds a specific change implementation task file.



POST /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;

```
{
    "guid": "I0K3HEIKVCT8RATCV2DU",
    "file": {
       "guid": "GYI1FCGITAT9SB0IJX9M",
       "number": "FILE-046012",
       "edition": "1",
       "name": "implementation plan.pdf",
       "storageMethodName": "FILE",
       "title": "Implementation Plan"
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
