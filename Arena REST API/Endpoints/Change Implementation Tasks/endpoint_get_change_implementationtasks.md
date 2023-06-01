# GET Change Implementation Tasks
/changes/&lt;GUID&gt;/implementationtasks

Returns the implementation tasks for a specific change category. Note that Implementation Task Management must be enabled for the category. If it is not enabled, the endpoints shall return an error indicating it is not enabled.

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
Get the implementation tasks of a specific change.

GET /changes/&lt;GUID&gt;/implementationtasks

```
{
    "count": 5,
    "results": [
        {
           "guid": "J1L4IFJLWDWZI0G8FQA8",
           "name": "Check Supplier",
           "assignee": {  
               "userGroup": {
                  "guid": "VDXGURVX8OUH0J2L4HEJ",
                  "name": "EveryHome Engineering USA"
               }
           },
           "dueDate": "2022-03-07T08:00:00Z",
           "status": "NOT_STARTED"  
           },
        {
           "guid": "J1L4IFJLWDWZI0G8FQA8",
           "name": "Verify Final Tooling",
           "assignee": {  },
               "supplier": {
                  "guid": "4M6P3046HXGM5OTJK65R",
                  "name": "Onward Technology Corp"
               },
           },
           "dueDate": "2022-03-07T08:00:00Z",
           "status": "NOT_STARTED"  
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
