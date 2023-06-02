# POST Ticket Create
/tickets

Users can assign a Ticket number in via the following methods.  

* Specify the numberSequencePrefix in the request body. User specifies the prefix while Arena auto-generates the next values to complete the Ticket number.

* Specify the number in the request body. User defines the entire Ticket number in the endpoint.

* User specifies neither of the above. The default numbering for the template will be used. If there are multiple sequences for the number, the first alphabetic prefix will be selected.

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
Create Ticket. Specify numberSequencePrefix.

POST /tickets

**Request** 

```
{
    "additionalAttributes": [
        {
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "value": "Model 20000"
        }
    ],
    "template": {
        "guid": "8QATCPA1OR83M5O7Q967"
    },
    "numberSequencePrefix": {
        "value": "DEF-"
    },
    "title": "Paint chipping on new Model 20000",
    "fixVersion": "2.0",
    "foundOn": "1.0",
    "priority": "Critical",
    "assignee": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
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
    "fixVersion": "2.0",
    "foundOn": "1.0",
    "guid": "1J3M5I3UHK1GZI1K31L4",
    "modifyDateTime": "2021-09-07T05:24:08Z",
    "title": "Paint chipping on new Model 20000",
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
Create Ticket. Specify entire ticket number.

POST /tickets

**Request** 

```
{
    "additionalAttributes": [
        {
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "value": "Model 20000"
        }
    ],
    "template": {
        "guid": "8QATCPA1OR83M5O7Q967"
    },
    "number": "DEF-000009",
    "title": "Paint chipping on new Model 20000",
    "fixVersion": "2.0",
    "foundOn": "1.0",
    "priority": "Critical",
    "assignee": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
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
        }
    ],
    "assignee": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "creationDateTime": "2021-09-07T05:25:10Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "description": "",
    "fixVersion": "2.0",
    "foundOn": "1.0",
    "guid": "1J3M5I3UHK1GZI1K31L4",
    "modifyDateTime": "2021-09-07T05:25:10Z",
    "title": "Paint chipping on new Model 20000",
    "number": "DEF-000009",
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
