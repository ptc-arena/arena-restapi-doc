# POST Tickets Add Change Reference
/tickets/&lt;GUID&gt;/changes

Adds a Change as a reference to a ticket.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Sample Request Body
```
{
    "change": {
        "guid": "CUEXGOODHCVYHZI360DQ"
    }
}
```
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
