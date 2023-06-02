# GET Extract
/extracts/&lt;GUID&gt;

Returns a single Extract object \(but not the extract run content\) for an extract with a given GUID.

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
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get a single extract with a given GUID

GET /extracts/N5P8RZ6S8GZRATCVEXEL

```
{  
   "creationDateTime":"2015-03-19T15:33:43Z",
   "creator":{  
      "fullName":"Everyroad API"
   },
   "enabled":true,
   "guid":"N5P8RZ6S8GZRATCVEXEL",
   "name":"October Change Cycle Time"
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
