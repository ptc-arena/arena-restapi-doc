# GET Supplier Addresses
/suppliers/&lt;GUID&gt;/addresses

Returns the addresses a Supplier object with a given GUID.

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get the addresses of a  supplier with a given GUID

/suppliers/&lt;GUID&gt;/addresses

```
{
    "count": 2,
    "results": [
        {
            "address": {
                "address1": "459 Embarcadero",
                "address2": null,
                "city": "San Francisco",
                "Country/Region": "United States",
                "guid": "5N7Q9M7YLOZ3M5GLXZ0K",
                "label": "SF Office",
                "postalCode": "94003",
                "province": null,
                "state": "CALIFORNIA"
            },
            "primary": false
        },
        {
            "address": {
                "address1": "No.37 Xiangyang Rd.",
                "address2": null,
                "city": "Taipei City",
                "Country/Region": "Taiwan",
                "guid": "ZH1K3G1SFITXGZBRWP1K",
                "label": "main",
                "postalCode": "100",
                "province": null,
                "state": null
            },
            "primary": false
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
