# GET Request Quality Processes


GET /requests/&lt;GUID&gt;/quality

GET /requests/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns a collection of   objects for a Request with a given GUID \(all Quality Processes in which the Request is an affected object\). If the endpoint is apprended with a valid GUID, it returns a specific Quality Process and the step information where a specific Request has been added as an affected object.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Responses
Get all quality processes that include a given request



GET /requests/0I2LQGHHQXGXGVRR5XND/quality

```
{
    "count": 2,
    "results": [
        {
            "guid": "6O8RAN8ZMP7I1K3LZHS1",
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
        },
        {
            "guid": "5N7Q9M7YLO6H0J2KYGR1",
            "notes": null,
            "qualityProcess": {
                "guid": "TBVEXAVM9CVRATCVO1X4",
                "name": "Everyroad bezels melted/burned",
                "number": "CAR-000008",
                "step": {
                    "guid": "UCWFYBWNADWSBUDWP2Y8",
                    "name": "Problem Description"
                },
                "type": null
            }
        }
    ]
}
```
Return a specific Quality Process and specific step where a specific Request has been added as an affected object.



GET /requests/&lt;GUID&gt;/quality/&lt;GUID&gt;

```
{
    "guid": "6O8RAN8ZMP7I1K3LZHS1",
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
