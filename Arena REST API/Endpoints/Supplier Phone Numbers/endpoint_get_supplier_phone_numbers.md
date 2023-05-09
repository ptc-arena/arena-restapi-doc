# GET Supplier Profile Phone Numbers


/suppliers/&lt;GUID&gt;/phonenumbers

Returns the phone numbers of a  object with a given GUID.

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
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Retrieves he phone numbers of a supplier with a given GUID



/suppliers/&lt;GUID&gt;/phonenumbers

```
{ 
    "count": 3,
    "results": [
        {
            "comment": null,
            "extension": null,
            "guid": "6O8RAN8ZMP02L4DEIMG2",
            "label": "main",
            "number": "+886-2-2332-4239"
        },
        {
            "comment": null,
            "extension": null,
            "guid": "8QATCPA1OR24N6FGKOHB",
            "label": "fax",
            "number": "+886-2-2391-5143"
        },
        {
            "comment": "SF Regional Office",
            "extension": "x2289",
            "guid": "8QATCPA1OR24N6DFIPX3",
            "label": "main",
            "number": "415-968-3232"
        }
    ]
}         
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
