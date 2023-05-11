# GET Changes Ticket References


/changes/&lt;GUID&gt;/tickets

/changes/&lt;GUID&gt;/tickets/&lt;GUID&gt;

Returns the Ticket References of a Change object. If the endpoint is appended with a valid GUID, it returns a single specific Change Ticket Reference.

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

## Sample Response Body
Get all the Ticket References associated with an Change of a given GUID.



GET /changes/&lt;GUID&gt;/tickets

```
{
    "count": 2,
    "results": [
        {
            "guid": "CUEXGTE5SVC6P8R9O93E",
            "ticket": {
                "guid": "GYI1KXI9WZGVEXGZI0K9",
                "number": "DEF-000002"
            }
        },
        {
            "guid": "HZJ2LYJAX0HBUDWETE84",
            "ticket": {
                "guid": "5N7Q9M7YLO5K3M5O7PAS",
                "number": "REQ-000004"
            }
        }
    ]
}
```
Get a single Ticket Reference  with a specific GUID associated with a Change with a specific GUID.



GET /changes/&lt;GUID&gt;/tickets/&lt;GUID&gt;

```
{
    "guid": "CUEXGTE5SVC6P8R9O93E",
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
