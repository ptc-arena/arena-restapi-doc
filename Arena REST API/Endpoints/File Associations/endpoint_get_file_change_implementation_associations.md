# GET File Change Implementation Associations
/files/&lt;GUID&gt;/changeimplementations

Returns a list of file association GUIDs \(and limited information about the associated Change\) for a File with a given GUID. 


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
