# GET Ticket Items
/tickets/&lt;GUID&gt;/items

/tickets/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a collection of  items added as references to a ticket   object. Appending a GUID to the URL returns the item with that GUID.

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
