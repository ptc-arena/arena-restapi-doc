# POST Ticket Status Change
/tickets/statuschanges

Users can change the status of a Ticket through this endpoint.  Supported statuses: NOT_STARTED, IN_PROGRESS, and COMPLETE.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Requests and Responses
Upgrade the status of a Ticket from NOT_STARTED to IN_PROGRESS.

POST /tickets/statuschanges

**Request** 

```
{
   "ticket": {
       "guid": "1J3M5I3UHK1GZI1K31L4"
    },
    "status": "IN_PROGRESS"
}
```
**Response** 

```
{
    "additionalAttributes": [
        {
            "apiName": "5N7Q9M7YLO5N6P8RATF6",
            "fieldType": "SINGLE_LINE_TEXT",
            "guid": "5N7Q9M7YLO5N6P8RATF6",
            "name": "Labels",
            "value": "Model 20000"
        },
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
    "modifyDateTime": "2021-09-07T06:13:33Z",
    "title": "Paint chipping on new Model 3000",
    "number": "DEF-000004",
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
