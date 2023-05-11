# GET A Specific Request Associated with a Change


/changes/&lt;GUID&gt;/requests/&lt;GUID&gt;

Returns a specific request associated with a specific change. Users must have a Read Change Summary and  Edit Change Requests rule for the Change. Additionally, users must have a Read Request Summary rule for the request being added.

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
Get a specific request associated with a change



GET /changes/&lt;GUID&gt;/requests/&lt;GUID&gt;

```
{
    "guid": "J1L4N4N3ZCUI1K3BE6EB",
    "request": {
        "guid": "N5P8R8R73GZYH0J024AP",
        "number": "ECR-000001"
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
