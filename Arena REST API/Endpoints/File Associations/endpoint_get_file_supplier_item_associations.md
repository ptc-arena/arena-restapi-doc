# GET File Supplier Item Associations


/files/&lt;GUID&gt;/supplieritems

Returns a list of Supplier Item association GUIDs \(and limited information about the associated Supplier Item\) for a File with a given GUID. 

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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get a File's Supplier Item  associations

 

GET &lt;url&gt;/files/&lt;GUID&gt;/supplieritems

```
{  
   "count":6,
   "results":[  
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
      },
      {  
         "guid":"KEYH0DYPCFWFYH0JSIPD",
         "supplierItem":{  
            "guid":"9J3M5I3UHK1M5O7Q9S0V",
            "number":"CBDY454A",
            "supplier":{  
               "guid":"QEYH0DYPCFWFYH0JSIPD",
               "name":"Cyberdyne Industries"
            }
         }
      },
      {  
         "guid":"AO8RAN8ZMP6Q9SBUDTFF",
         "supplierItem":{  
            "guid":"7P9SBO90NQ9H0F3XUEJR",
            "number":"VAR454A",
            "supplier":{  
               "guid":"VRX38YZZ8FY4N6B122AL",
               "name":"Variance Inc"
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
