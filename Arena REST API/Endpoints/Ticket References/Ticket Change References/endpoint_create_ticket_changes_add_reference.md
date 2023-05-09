# POST Tickets Add Change Reference


/tickets/&lt;GUID&gt;/changes

Adds a Change as a reference to a ticket.

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

## Sample Request Body
```
{
    "change": {
        "guid": "CUEXGOODHCVYHZI360DQ"
    }
}
```
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
Adds a Change as a reference to a ticket.



POST &lt;url&gt;/tickets/&lt;GUID&gt;/changes

```
{
    "change": {
        "guid": "CUEXGOODHCVYHZI360DQ",
        "number": "DCO-000001"
    },
    "guid": "O6Q9S5QH47OI1K3HK2JR"
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
