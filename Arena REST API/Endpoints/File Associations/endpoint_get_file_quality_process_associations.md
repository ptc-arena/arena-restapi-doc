# GET File Quality Process Associations
/files/&lt;GUID&gt;/qualityprocesses

Returns a list of Quality Process association GUIDs \(and limited information about the associated Quality Processes\) for a File with a given GUID. 

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
Get a File's Quality Process  associations

GET &lt;url&gt;/files/&lt;GUID&gt;/qualityprocesses

```
{  
   "count":6,
   "results":[  
      {  
         "guid":"9RBUZPQQZ6N3M5O79TKC",
         "qualityProcess":{  
            "guid":"4M6PUKLLU1KGZI1KYBRS",
            "number":"NCMR-000002",
            "step":{  
               "guid":"6O8RWMNNW3MI1K3M0DT2",
               "name":"Action Taken"
            }
         }
      },
      {  
         "guid":"DFR16WXX6DUDWFYHPRY3",
         "qualityProcess":{  
            "guid":"XFZINDEENUD9SBUDTFH4",
            "number":"8D-000003",
            "step":{  
               "guid":"YG0JOEFFOVEATCVEUGI5",
               "name":"Action Taken"
            }
         }
      },
      {  
         "guid":"2UV4N6J4VIL40J2L4N0B3",
         "qualityProcess":{  
            "guid":"K2M5O1MD03ML1K3MVZIC",
            "number":"CAR-000003",
            "step":{  
               "guid":"Q6Q9S5QH47QMFO7QZ3MG",
               "name":"Immediate Containment"
            }
         }
      },
      ...
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
