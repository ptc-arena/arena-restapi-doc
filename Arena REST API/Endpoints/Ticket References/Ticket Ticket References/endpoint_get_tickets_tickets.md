# GET Ticket Tickets


/tickets/&lt;GUID&gt;/tickets

/tickets/&lt;GUID&gt;/tickets/&lt;GUID&gt;

Returns a collection of  tickets added as references to a ticket   object. Appending a GUID to the URL returns the ticket with that GUID.

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
Get all tickets added as references to a  ticket



GET /tickets/&lt;GUID&gt;/tickets

```
{
    "count": 3,
    "results": [
        {
            "guid": "7P9SBO90NQ71K3M4ILKN",
            "ticket": {
                "guid": "GYI1KXI9WZGVEXGZI0K9",
                "number": "DEF-000002"
            }
        },
        {
            "guid": "5N7Q9M7YLO5ZI1K2GJIL",
            "ticket": {
                "guid": "YG0J2F0REHYDWFYH0YI1",
                "number": "DEF-000003"
            }
        },
        {
            "guid": "2K4N6J4VIL2WFYHZDGG5",
            "ticket": {
                "guid": "4M6P8L6XKN4J2L4N64OR",
                "number": "DEF-000005"
            }
        }
    ]
}
```
Get  a specific ticket with a specific GUID added as a reference to a ticket of a specific GUID



GET /tickets/&lt;GUID&gt;/tickets/&lt;GUID&gt;

```
{
    "guid": "7P9SBO90NQ71K3M4ILKN",
    "ticket": {
        "guid": "GYI1KXI9WZGVEXGZI0K9",
        "number": "DEF-000002"
    }
}
```
