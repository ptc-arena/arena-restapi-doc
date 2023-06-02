# GET All Changes Associated with a Request
/requests/&lt;GUID&gt;/changes

Returns all  the changes associated with a specific request.  Users must have a Read Request Summary and  Edit Request Changes rule. Additionally users must have a  Read Change Summary rule for the referenced changes.

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
Get all changes associated with a request.

GET /requests/&lt;GUID&gt;/changes

```
{
    "count": 4,
    "results": [
        {
            "change": {
                "guid": "YG0J2J2IERADWEXIMLIS",
                "number": "ECO-000033"
            },
            "guid": "FXH0J0JZV8QEXGZ7AQVD"
        },
        {
            "change": {
                "guid": "DVFYHYHXT6PSBTCX10WY",
                "number": "DEV-000003"
            },
            "guid": "O6Q9S9S84HZN6P8GJBI8"
        },
        {
            "change": {
                "guid": "UCWFYFYEAN69SATEIHDS",
                "number": "ECO-000044"
            },
            "guid": "N5P8R8R73GYM5O7FIAHU"
        },
        {
            "change": {
                "guid": "CUEXGXGWS5ORASBW0ZVR",
                "number": "ECO-000041"
            },
            "guid": "P7RATAT95I0O7Q9HKCJT"
        }
    ]
} 
```
Request with invalid GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
