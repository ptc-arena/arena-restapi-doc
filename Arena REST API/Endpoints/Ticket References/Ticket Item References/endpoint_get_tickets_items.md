# GET Ticket Items


/tickets/&lt;GUID&gt;/items

/tickets/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a collection of  items added as references to a ticket   object. Appending a GUID to the URL returns the item with that GUID.

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
Get all items added as references to a  ticket



GET /tickets/&lt;GUID&gt;/items

```
{
    "count": 3,
    "results": [
        {
            "guid": "UCWFYBWNADUO7Q9R58AA",
            "item": {
                "guid": "WEYH0DYPCFY6P4SMJ3DL",
                "name": "SOP, Risk Management",
                "number": "020-00006",
                "revision": "A",
                "revisionStatus": "EFFECTIVE"
            }
        },
        {
            "guid": "WEYH0DYPCFWQ9SBT7ACL",
            "item": {
                "guid": "7P9SBO90NQ9H0F3XUEJR",
                "name": "SOP, Production and Process Management",
                "number": "020-00008",
                "revision": "A",
                "revisionStatus": "EFFECTIVE"
            }
        },
        {
            "guid": "VDXGZCXOBEVP8RAS69BZ",
            "item": {
                "guid": "HZJ2LYJAX0JRAPD74OXR",
                "name": "SOP, Supplier Quality Management",
                "number": "020-00007",
                "revision": "A",
                "revisionStatus": "EFFECTIVE"
            }
        }
    ]
}
```
Get  a specific item with a specific GUID added as a reference to a ticket of a specific GUID



GET /tickets/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "UCWFYBWNADUO7Q9R58AA",
    "item": {
        "guid": "WEYH0DYPCFY6P4SMJ3DL",
        "name": "SOP, Risk Management",
        "number": "020-00006",
        "revision": "A",
        "revisionStatus": "EFFECTIVE"
    }
}
```
