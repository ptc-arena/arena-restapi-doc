# GET A Specific Change Associated with a Request
/requests/&lt;GUID&gt;/changes/&lt;GUID&gt;

Returns a specific change associated with a specific request. Users must have a Read Request Summary and  Edit Request Changes rule. Additionally users must have a  Read Change Summary rule for the referenced changes.

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
