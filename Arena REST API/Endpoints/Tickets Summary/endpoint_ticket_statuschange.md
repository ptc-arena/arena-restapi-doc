# POST Ticket Status Change
/tickets/statuschanges

Users can change the status of a Ticket through this endpoint.  Supported statuses: NOT_STARTED, IN_PROGRESS, and COMPLETE.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
