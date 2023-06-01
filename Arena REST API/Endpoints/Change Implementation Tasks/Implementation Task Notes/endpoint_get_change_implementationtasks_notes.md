# GET Change Implementation Task Notes
/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID/notes

Returns the notes in a specific implementation task within a specific change. Only supported in categories that have Implementation Task Management enabled.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
