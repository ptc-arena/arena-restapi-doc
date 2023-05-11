# GET Change Implementation Task Note


/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes/&lt;GUID&gt;

Returns a specific note in a specific implementation task of a specific change. Only supported in categories that have Implementation Task Management enabled.

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
Get a specific implementation task note.



GET /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes/&lt;GUID&gt;

```
{
   "guid": "I0K3HEIKVCT8RATCV2DU",
   "note" "This was done early to help schedule.",
   "private": True,
   "label": "Cost Impact"
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
