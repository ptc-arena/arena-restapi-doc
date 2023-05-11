# POST Supplier Profile Address Create


/suppliers/&lt;GUID&gt;/addresses

Creates  new addresses for a   object. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{
    "address": {
        "address1": "1738 Lundy Ave.",
        "address2": null,
        "city": "San Jose",
        "Country/Region": "United States",
        "label": "Main",
        "postalCode": "95131",
        "province": null,
        "state": "CALIFORNIA"
    },
    "primary": false
}   
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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
Create a new supplier address.



/suppliers/&lt;GUID&gt;/addresses

```
 {
    "address": {
        "address1": "1738 Lundy Ave.",
        "address2": null,
        "city": "San Jose",
        "Country/Region": "United States",
        "guid": "0I2L4CLLIZISBUDUIUI4"
        "label": "Main",
        "postalCode": "95131",
        "province": null,
        "state": "CALIFORNIA"
    },
    "primary": false
}    
```
Request with invalid Country/Region or state

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3045,
            "message":"The Country/Region or state is invalid for the supplier address."
        }
    ]
}
```
