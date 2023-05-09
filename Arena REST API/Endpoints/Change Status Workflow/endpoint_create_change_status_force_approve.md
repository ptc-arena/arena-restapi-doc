# POST Change Status (Force Approve)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to force approve a Change. Only Change Administators can perform this version of this endpoint. 

For changes that have reached a status of SUBMITTED_FOR_APPROVAL, a Change administrator can force approve the change by inputting a value of APPROVED for the status attribute  within the request body of the POST Change Status endpoint.

In an API Force Approval, the request body inputs a value of APPROVED,  yet the response body returns a status of EFFECTIVE. This reflects a unique behavior within Arena's Change lifecycle: Once a Change is approved, it automatically becomes effective in an automated step.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Requests and Responses
For Change administrators, inputting a status of APPROVED in a Change that has a status of SUBMITTED_FOR_APPROVAL force approves the change.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E"
    },
    "comment": "ECO-000022 is Submitted for Approval. Force Approving by Executive authority.",
    "status": "APPROVED"
}
```


```
{
    "administrators": [
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        }
    ],
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E",
        "number": "ECO-000022"
    },
    "comment": "ECO-000022 is Submitted for Approval. Force Approving by Executive authority.",
    "status": "EFFECTIVE"
}
```
