# GET Ticket Changes


/tickets/&lt;GUID&gt;/changes

/tickets/&lt;GUID&gt;/changes/&lt;GUID&gt;

Returns a collection of  changes added as references to a Ticket   object. Appending a GUID to the URL returns the change with that GUID.

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
