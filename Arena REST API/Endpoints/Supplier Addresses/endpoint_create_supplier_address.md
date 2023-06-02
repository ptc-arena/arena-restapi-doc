# POST Supplier Profile Address Create
/suppliers/&lt;GUID&gt;/addresses

Creates  new addresses for a  Supplier object. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
