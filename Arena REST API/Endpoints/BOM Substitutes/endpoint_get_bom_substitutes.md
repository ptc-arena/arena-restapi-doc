# GET BOM Subsitutes
/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes

Returns a BOM Substitute object with a given GUID, the immediate child of an assembly with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/x-www-form-urlencoded<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes<br> | true or false<br> | If this is true, the response returns empty additional attributes. The default is false.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> |   |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all the BOM Substitutes in within a BOM Line

/items/&lt;GUID&gt;/bom/&lt;GUID&gt;/substitutes

```
{
    "count": 2,
    "results": [
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
        },
        {
            "guid": "7P9SBO90NQ8Q9S5ETQ3G",
            "item": {
                "guid": "7P9SBO90NQ9H0ISBNH69",
                "name": "Voltage Regulator, Low-dropout, 5.0V, 100mA",
                "number": "160-00004",
                "revisionNumber": "01",
                "revisionStatus": "EFFECTIVE"
            },
            "notes": null,
            "quantity": 1,
            "rank": 2
        }
    ]
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
