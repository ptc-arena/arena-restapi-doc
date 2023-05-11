# GET Supplier Profile Phone Numbers


/suppliers/&lt;GUID&gt;/phonenumbers

Returns the phone numbers of a  object with a given GUID.

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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
