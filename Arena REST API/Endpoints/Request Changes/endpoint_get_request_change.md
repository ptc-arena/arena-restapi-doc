# GET A Specific Change Associated with a Request
/requests/&lt;GUID&gt;/changes/&lt;GUID&gt;

Returns a specific change associated with a specific request. Users must have a Read Request Summary and  Edit Request Changes rule. Additionally users must have a  Read Change Summary rule for the referenced changes.

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
Get a specific change associated with a request.

GET /requests/&lt;GUID&gt;/changes/&lt;GUID&gt;

```
{
    "change": {
        "guid": "8QATCTCSO1KN6P8PR972",
        "number": "ECO-000010"
    },
    "guid": "K2M5O5O40DVJ2L4CF7F5"
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
