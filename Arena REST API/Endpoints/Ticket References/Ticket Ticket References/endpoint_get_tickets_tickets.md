# GET Ticket Tickets
/tickets/&lt;GUID&gt;/tickets

/tickets/&lt;GUID&gt;/tickets/&lt;GUID&gt;

Returns a collection of  tickets added as references to a ticket   object. Appending a GUID to the URL returns the ticket with that GUID.

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

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
