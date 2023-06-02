# GET Ticket Quality Processes
/tickets/&lt;GUID&gt;/quality

/tickets/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns a collection of  quality processes added as references to a ticket   object. Appending a GUID to the URL returns the quality process with that GUID.

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
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all quality processes added as references to a  ticket

GET /tickets/&lt;GUID&gt;/quality

```
{
    "count": 3,
    "results": [
        {
            "guid": "0I2L4H2TGJ0UDWFXBEE0",
            "quality": {
                "guid": "FXH0JWH8VYHDWFYHTKDW",
                "number": "NCMR-000002",
                "step": {
                    "guid": "GYI1KXI9WZIEXGZIULEF",
                    "name": "Nonconformance Description"
                }
            }
        },
        {
            "guid": "YG0J2F0REHYSBUDV9CCH",
            "quality": {
                "guid": "K2M5O1MD03MI1K3MVZIC",
                "number": "CAR-000003",
                "step": {
                    "guid": "P7RAT6RI58RN6P8R04NA",
                    "name": "Corrective Action"
                }
            }
        },
        {
            "guid": "WEYH0DYPCFWQ9SBT7AAJ",
            "quality": {
                "guid": "0I2L4H2TGJ2YH0J2V0B1",
                "number": "CAR-000004",
                "step": {
                    "guid": "5N7Q9M7YLO73M5O705GA",
                    "name": "Corrective Action"
                }
            }
        }
    ]
}
```
Get  a specific quality process with a specific GUID added as a reference to a ticket of a specific GUID

GET /tickets/&lt;GUID&gt;/quality/&lt;GUID&gt;

```
{
    "guid": "0I2L4H2TGJ0UDWFXBEE0",
    "quality": {
        "guid": "FXH0JWH8VYHDWFYHTKDW",
        "number": "NCMR-000002",
        "step": {
            "guid": "GYI1KXI9WZIEXGZIULEF",
            "name": "Nonconformance Description"
        }
    }
}
```
