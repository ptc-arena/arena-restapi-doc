# POST Change Implementation Task Note


/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes

Adds a note to a change implementation task. Implementation Task Management must be enabled to execute this endpoint. Not supported for Canceled or Completed Changes.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
Adds a note to an implementation task.

```
{
    "note" "This was done early to help schedule.",
    "private": True,  
    "label": "Cost Impact"
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Adds a specific change implementation task note.



POST /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;/notes

```
{
    "guide": I0K3HEIKVCT8RATCV2DU,
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
