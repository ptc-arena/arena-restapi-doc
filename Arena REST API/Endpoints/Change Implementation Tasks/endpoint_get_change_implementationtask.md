# GET Change Implementation Task


/changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;

Returns an implementation task for a specific change category. Note that Implementation Task Management must be enabled for the category. If it is not enabled, the endpoints shall return an error indicating it is not enabled.

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
Get a specific implementation task.



GET /changes/&lt;GUID&gt;/implementationtasks/&lt;GUID&gt;

```
{
           "guid": "J1L4IFJLWDWZI0G8FQA8",
           "name": "Commit changes to archive",
           "assignee": {  
               "userGroup": {
                  "guid": "VDXGURVX8OUH0J2L4HEJ",
                  "name": "EveryHome Engineering USA"
               }
           },
           "dueDate": "2022-03-07T08:00:00Z",
           "status": "DONE"  
]
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
