# GET File Change Implementation Associations
/files/&lt;GUID&gt;/changeimplementations

Returns a list of file association GUIDs \(and limited information about the associated Change\) for a File with a given GUID. 


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
Change Implementation  Associations

GET &lt;url&gt;/files/&lt;GUID&gt;/changeimplementations

```
{
    "count": 3,
    "results": [
        {
            "change": {
                "guid": "5N7QVLNO10JM5N36I97P",
                "number": "ECO-000621"
            },
            "guid": "J1L49Z12FEV2L4G0BHZW"
        },
        {
            "change": {
                "guid": "CUEX2SUV87QTCUA2CVF8",
                "number": "ECO-001452"
            },
            "guid": "VDXGLBDERQ7EXGSCNLHO"
        },
        {
            "change": {
                "guid": "O6Q9E467KJ25O6MG49QC",
                "number": "ECO-001446"
            },
            "guid": "TBVEJ9BCPO5CVEQAM4SC"
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
