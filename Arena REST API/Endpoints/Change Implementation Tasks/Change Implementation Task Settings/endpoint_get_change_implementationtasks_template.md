# GET Change Implementation Task Template


/settings/changes/categories/&lt;GUID&gt;/implementationtemplates/&lt;GUID&gt;

Returns the implementation tasks template for a change. Implementation Task Management needs to be enabled for the category.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
Get a specific implementation task template of a specific change category.



GET /settings/changes/categories/&lt;GUID&gt;/implementationtemplates/&lt;GUID&gt;

```
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
