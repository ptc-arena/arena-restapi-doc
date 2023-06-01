# GET Ticket
/tickets/&lt;GUID&gt;

Returns a Ticket object with a given GUID.

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
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get a ticket with a unique GUID

GET /tickets/&lt;GUID&gt; 

```
{
    "additionalAttributes": [
        {
            "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
            "fieldType": "SINGLE_LINE_TEXT",
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "name": "Components",
            "value": null
        },
        {
            "apiName": "5N7Q9M7YLO5N6P8RATF6",
            "fieldType": "SINGLE_LINE_TEXT",
            "guid": "5N7Q9M7YLO5N6P8RATF6",
            "name": "Labels",
            "value": null
        }
    ],
    "assignee": {
        "email": "jparker@everyroadgps.com",
        "fullName": "John Parker",
        "guid": "XFZI1EZQDGXGZI1KTJQ2"
    },
    "creationDateTime": "2017-03-17T22:48:02Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "description": "<p>The power draw is too high on the 500 board, violating the requirement.</p>",
    "fixVersion": null,
    "foundOn": null,
    "guid": "GYI1KXI9WZGVEXGZI0K9",
    "modifyDateTime": "2017-03-21T23:32:18Z",
    "title": "500 board drawing 10.5V",
    "number": "DEF-000002",
    "priority": "Critical",
    "status": {
        "guid": "R9TCV8TK7ARN6P8RATDZ",
        "value": "In Progress"
    },
    "template": {
        "guid": "8QATCPA1OR83M5O7Q967",
        "name": "Defects"
    }
}
```
Request with bad GUID

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
