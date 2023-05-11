# PUT Ticket Edit


/tickets/&lt;GUID&gt;

Updates  information for a Tickets with a given GUID. 

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

## Sample Requests and Responses
Edit a Ticket.

PUT /requests/&lt;GUID&gt;



```
{
    "additionalAttributes": [
        {
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "value": "Model 3000"
        }
    ],
    "title": "Paint chipping on new Model 3000",
    "fixVersion": "3.0",
    "foundOn": "2.0",
    "priority": "Critical",
    "assignee": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```


```
{
    "additionalAttributes": [
        {
            "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
            "fieldType": "SINGLE_LINE_TEXT",
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "name": "Components",
            "value": "Model 3000"
        }
    ],
    "assignee": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "creationDateTime": "2021-09-07T05:24:08Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "description": "",
    "fixVersion": "3.0",
    "foundOn": "2.0",
    "guid": "1J3M5I3UHK1GZI1K31L4",
    "modifyDateTime": "2021-09-07T05:51:59Z",
    "title": "Paint chipping on new Model 3000",
    "number": "DEF-000004",
    "priority": "Critical",
    "status": {
        "guid": "Q8SBU7SJ69QM5O7Q9SCG",
        "value": "Not Started"
    },
    "template": {
        "guid": "8QATCPA1OR83M5O7Q967",
        "name": "Defects"
    }
}
```
Request with invalid GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3011,
            "message":"The guid \"ASCVERC3QTCFYGPWW1WCS\" is not valid"
        }
    ]
}
```
