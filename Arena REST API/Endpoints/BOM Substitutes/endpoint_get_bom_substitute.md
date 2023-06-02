# GET BOM Subsitute
/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes/&lt;GUID&gt;

Returns a BOM Substitute object with a given GUID, the immediate child of an assembly with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/x-www-form-urlencoded  |   |


| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes  | true or false  | If this is true, the response returns empty additional attributes. The default is false.  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  |   |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all the BOM Substitutes in within a BOM Line.

/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes/&lt;GUID&gt;

```
{
    "guid": "2K4N6J4VIL3L4N09ONJK",
    "item": {
        "guid": "2K4N6J4VIL4CVA8EYV18",
        "name": "Voltage Regulator, Low-dropout, 5.0V, 90µA",
        "number": "160-00007",
        "revisionNumber": "1",
        "revisionStatus": "EFFECTIVE"
    },
    "notes": "This regulator is more costly but has a better dropout.",
    "quantity": 1,
    "rank": 1
}
```
Request with a bad GUID.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"WEYH08HHEVEL4N6F52Sf\" is not valid."
    }
  ]
}
```
