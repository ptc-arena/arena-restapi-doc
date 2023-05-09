# GET File Item Association


/files/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a specific item association GUIDs  for a File with a given GUID. 

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
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
A specific file item association.

GET &lt;url&gt;/files/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{  
   "guid":"7P9SXNOOX4NRATE1TMVN",
   "items":[  
      {  
         "guid":"1J3MRHIIRYHRAT5D1U08",
         "number":"100-91",
         "revisionNumber":"A",
         "status":2
      },
      {  
         "guid":"J1L49Z009GY1K3M5OHYM",
         "number":"100-91",
         "revisionNumber":"B",
         "status":1
      },
      {  
         "guid":"FXH05VWW5CV4N6MNGHDF",
         "number":"100-91",
         "revisionNumber":"C",
         "status":0
      }
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
