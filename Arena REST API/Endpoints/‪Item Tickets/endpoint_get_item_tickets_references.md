# GET Item Ticket References
/items/&lt;GUID&gt;/tickets

/items/&lt;GUID&gt;/tickets/&lt;GUID&gt;

Returns the Ticket References of an Item object. If the endpoint is appended with a valid GUID, it returns a single specific Item Ticket Reference.

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
Get all the Ticket References associated with an Item of a given GUID.

GET /items/&lt;GUID&gt;/tickets

```
{
    "count": 3,
    "results": [
        {
            "guid": "0I2L4H2TGJ0UDWFXCXR5",
            "ticket": {
                "guid": "5N7Q9M7YLO5K3M5O7PAS",
                "number": "REQ-000004"
            }
        },
        {
            "guid": "ZH1K3G1SFIZTCVEWBWQV",
            "ticket": {
                "guid": "ASCVERC3QTAP8RATCUF0",
                "number": "REQ-000005"
            }
        },
        {
            "guid": "1J3M5I3UHK1VEXGYDYSE",
            "ticket": {
                "guid": "GYI1KXI9WZGVEXGZI0K9",
                "number": "DEF-000002"
            }
        }
    ]
}
```
Get a single Ticket Reference  with a specific GUID associated with an Item with a specific GUID.

GET /items/&lt;GUID&gt;/tickets/&lt;GUID&gt;

```
{
    "guid": "1J3M5I3UHK1VEXGYDYSE",
    "ticket": {
        "guid": "GYI1KXI9WZGVEXGZI0K9",
        "number": "DEF-000002"
    }
}
```
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
