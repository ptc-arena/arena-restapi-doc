# GET Supplier Item Quality Processes
GET /supplieritems/&lt;GUID&gt;/quality

GET /supplieritems/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns an array of  Quality Process objects for a Supplier Item with a given GUID \(all Quality Processes in which the Supplier Item is an affected object\). 

If the endpoint is apprended with a valid GUID, it returns a specific Quality Process and the step information where the specified Supplier has been added as an affected object.

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
Get all quality processes that include a given supplier item

GET /supplieritems/0I2LQGHHQXGXGVRR5XND/quality

```
{  
   "count":1,
   "results":[  
      {  
         "guid":"4M6PUJ0E1K1H0J2LUOPL",
         "notes":null,
         "qualityProcess":{  
            "guid":"DVFYHPYYCT9SBUDV023",
            "notes":"main PCBA in question",
            "name":"FAI Failure: 056-0003 Everyroad Rear Panel",
            "number":"FAFR-000001",
            "step":{  
               "guid":"TBVEJ8P3Q9SO7Q9S68C4",
               "name":"Gather Data"
            },
            "type":"Severe"
         }
      }
   ]
}
```
Gets a specific Quality Process \(and specific step information\) where the specified Supplier Item has been added as an affected object.

GET /supplieritems/&lt;GUID&gt;/quality/&lt;GUID&gt;

```
{
    "guid": "ZH1K3G1SFI0BUDWESALZ",
    "notes": null,
    "qualityProcess": {
        "guid": "M4O7Q3OF25OK3M5OHUQ2",
        "name": "Manufacturing flaws on 175-00001 boards",
        "number": "CAR-000007",
        "step": {
            "guid": "N5P8R4PG36PL4N6PIVRR",
            "name": "Problem Description"
        },
        "type": null
    }
}
```
Produces an error if the GUID is not valid.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"0I2LQGHHQXGXGVRR5XND\" is not valid."
      }
   ]
}
```
