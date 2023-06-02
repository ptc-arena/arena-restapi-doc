# GET File Supplier Item Association
/files/&lt;GUID&gt;/supplieritems/&lt;GUID&gt;

Returns a  supplier item association GUID for a file with a given GUID. 

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
File Supplier Item  association

GET &lt;url&gt;/files/&lt;GUID&gt;/supplieritems/&lt;GUID&gt;

```
{  
   "guid":"O6Q9E455EL37Q95FRH30",
   "supplierItem":{  
      "guid":"O6Q9E455EL49SBB1KF69",
      "number":"AQW454A",
      "supplier":{  
         "guid":"I0K38YZZ8FY4N6B122AL",
         "name":"Aromat"
         }
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
