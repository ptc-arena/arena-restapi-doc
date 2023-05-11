# GET Ticket Changes


/tickets/&lt;GUID&gt;/changes

/tickets/&lt;GUID&gt;/changes/&lt;GUID&gt;

Returns a collection of  changes added as references to a Ticket   object. Appending a GUID to the URL returns the change with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all changes added as references to a specific  ticket



GET /tickets/&lt;GUID&gt;/changes

```
{
    "count": 3,
    "results": [
        {
            "change": {
                "guid": "BTDWFSD4RUDGZHX2V463",
                "number": "MCO-000004"
            },
            "guid": "FXH0JWH8VYF9SBUCQTT8"
        },
        {
            "change": {
                "guid": "4M6P8L6XKN69SAQQTS0P",
                "number": "MCO-000008"
            },
            "guid": "EWGZIVG7UXE8RATBPSS9"
        },
        {
            "change": {
                "guid": "5N7Q9M7YLO7ATBRRUT1K",
                "number": "MCO-000009"
            },
            "guid": "DVFYHUF6TWD7Q9SAORRW"
        }
    ]
}
```
Get  a specific change with a specific GUID added as a reference to a ticket of a specific GUID



GET /tickets/&lt;GUID&gt;/changes/&lt;GUID&gt;

```
{
    "change": {
        "guid": "BTDWFSD4RUDGZHX2V463",
        "number": "MCO-000004"
    },
    "guid": "FXH0JWH8VYF9SBUCQTT8"
}
```
