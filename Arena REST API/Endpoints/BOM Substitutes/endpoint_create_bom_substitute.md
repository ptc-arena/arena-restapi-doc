# POST BOM Substitute Create


/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes

Creates a new  BOM Substitute for an item with a given GUID. Only the working reivision of the parent Item can be modified with BOM Substitutes. Items must be released to be specified as a subtitute. BOM Substitutes can be superseded revisions of the child Item. Existing BOM Substitutes can not be added again to the same BOM Line.

Rank is a positive integeter between one and the total number of substitutes. If the user specifies a rank that already exists, the new BOM Substitute will be assigned that rank and the ranks of all other substitutes that have a higher rank value \(including the BOM Substitute that previously had the specified rank value\) will be incremented by one. If rank is not specified in the POST, it is set to the last rank.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
Add BOM Substitute

```
{
    "quantity": 1,
    "rank": 1,
    "notes": "Only when primary supply is exhausted",
    "item":{
        "guid":"DVFYHUF6TWFN6K28U3ZP"
    }
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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
Add BOM Substitute



/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes

```
{
    "guid": "L3N6P2NE14M4N6JQ5ORH",
    "item": {
        "guid": "DVFYHUF6TWFN6K28U3ZP",
        "name": "Voltage Regulator, Low-dropout, 5.0V, 90µA",
        "number": "160-00009",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE"
    },
    "notes": "Only when primary supply is exhausted",
    "quantity": 1,
    "rank": 1
}
```
Attempting to add BOM Substitute to locked BOM

```
{
    "status": 400,
    "errors": [
        {
            "code": 3034,
            "message": "The item is locked."
        }
    ]
}
```
