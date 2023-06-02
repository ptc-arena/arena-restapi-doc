# GET File Supplier Item Associations
/files/&lt;GUID&gt;/supplieritems

Returns a list of Supplier Item association GUIDs \(and limited information about the associated Supplier Item\) for a File with a given GUID. 

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
