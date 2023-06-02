# GET Change Implementation Task Notes
/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID/notes

Returns the notes in a specific implementation task within a specific change. Only supported in categories that have Implementation Task Management enabled.

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
Get the notes of a specific change implementation task.

GET /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes

```
{
    "count": 20,
    "results": [
        {
           "guid": "I0K3HEIKVCT8RATCV2DU",
           "note" "This was done early to help schedule.",
           "private": True,
           "label": "Cost Impact"
        },
        {
           "guid": "5N7Q4157IZGZI1K33VOE",
           "note" "Done per the request of our Validation team.",
           "private": True,
           "label": "Quality Control"
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
