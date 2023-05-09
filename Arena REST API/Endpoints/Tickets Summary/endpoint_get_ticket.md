# GET Ticket


/tickets/&lt;GUID&gt;

Returns a Ticket object with a given GUID.

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
