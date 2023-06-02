# GET Change Implementation Task Note
/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes/&lt;GUID&gt;

Returns a specific note in a specific implementation task of a specific change. Only supported in categories that have Implementation Task Management enabled.

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
