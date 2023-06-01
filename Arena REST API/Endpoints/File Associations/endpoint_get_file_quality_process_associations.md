# GET File Quality Process Associations
/files/&lt;GUID&gt;/qualityprocesses

Returns a list of Quality Process association GUIDs \(and limited information about the associated Quality Processes\) for a File with a given GUID. 

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
