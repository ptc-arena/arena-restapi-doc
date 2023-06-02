# GET Item Quality Processes
GET /items/&lt;GUID&gt;/quality

GET /items/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns a collection of  Quality Process objects for an item with a given GUID \(all Quality Processes in which the Item is an affected object\). If the endpoint is apprended with a valid GUID, it returns a specific Quality Process and the step information where a specific Item has been added as an affected object.

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

## Sample Responses
Get all quality processes that include a given item

GET /items/0I2LQGHHQXGXGVRR5XND/quality

```
{  
   "count":1,
   "results":[  
      {  
         "guid":"L3N6B0HVI1IYH0J2B57U",
         "notes":"This is the related Quality process",
         "qualityProcess":{  
            "creationDateTime":null,
            "guid":"SAUDI7O2P8RN6P8R57B7",
            "name":"Quality Issue on 500 board",
            "number":"8D-000002",
            "step":{  
               "guid":"TBVEJ8P3Q9SO7Q9S68C4",
               "name":"Form Team"
            },
            "type":"8D"
         }
      }
   ]
}
```
Return a specific Quality Process and specific step where a specific Item has been added as an affected object.

GET /items/&lt;GUID&gt;/quality/&lt;GUID&gt;

```
{
    "guid": "XFZI1EZQDGY9SBUCQ8JJ",
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
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
