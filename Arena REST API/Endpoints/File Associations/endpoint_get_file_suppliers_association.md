# GET File Supplier Association
/files/&lt;GUID&gt;/suppliers/&lt;GUID&gt;

Returns a   File Supplier association GUID  for a File with a given GUID. 

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
A specific File Suppliers  Association

GET &lt;url&gt;/files/&lt;GUID&gt;/suppliers/&lt;GUID&gt;

```
{  
  "guid":"5N7QVLMMV2JRATA2GJ6E",
  "supplier":{  
     "guid":"UCWFKABBKRAGZINDEEM1",
     "name":"Avnet"
     }
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
