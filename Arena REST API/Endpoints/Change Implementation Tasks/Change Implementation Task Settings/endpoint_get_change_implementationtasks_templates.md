# GET Change Implementation Task Templates


/settings/changes/categories/&lt;GUID&gt;/implementationtemplates

Returns the implementation tasks template for a change. Implementation Task Management needs to be enabled for the category.

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
Get the implementation task templates of a specific change category.



GET /settings/changes/categories/&lt;GUID&gt;/implementationtemplates

```
{
    "count": 7,
    "results": [
        {
          "guid": "L3N6KHLNYFY8RAQ8SWYT",
          "name": "Check Supplier",
          "defaultAssignee": {  
               "user": {
                   "email": "rolu@ptc.com",
                   "fullName": "Rocky Lu",
                   "guid": "5N7Q4157IZGZI1K33VOE"
               },
          }
        },
        {
          "guid": "L3N6KHLNYFY8RAQ8SWYT",
          "name": "Check Supplier",
          "defaultAssignee": {  
               "userGroup": {
                   "guid": "VDXGURVX8OUH0J2L4HEJ",
                   "name": "Supplier & Supplier Item Manager"
               }
          }
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
