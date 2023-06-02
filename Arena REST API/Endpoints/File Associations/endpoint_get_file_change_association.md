# GET File Change Association
/files/&lt;GUID&gt;/changereferences/&lt;GUID&gt;

Returns a Change File association GUID \(and information about the associated Change\) for a File with a given GUID. 

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
Change Reference  Association

GET &lt;url&gt;/files/&lt;GUID&gt;/changereferences/&lt;GUID&gt;

```
{
    "change": {
        "guid": "CUEX2SUV87QTCUA2CVF8",
        "number": "ECO-001452"
    },
    "guid": "I0K38Y01EDU1K3YHEUEL"
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
