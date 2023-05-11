# POST Requests Status Change (Submitted to Closed)


/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Closed. This endpoint example is equivalent to closing a submitted Request within the browser\-based application.

Note that Requests created by supplier users contain an additional property, labeled resolutionNotes, within their responses when closed.

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
Upgrade the status of a Request from SUBMITTED to CLOSED.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "L3N6P2NE14NM5OK430OS"
    },
    "comment": "From Submitted to Closed",
    "status": "CLOSED",
    "resolutionCode": "As Designed"
}
```


```
{
    "comment": "From Submitted to Closed",
    "request": {
        "guid": "L3N6P2NE14NM5OK430OS",
        "number": "ECR-000010"
    },
    "resolutionCode": "As Designed",
    "status": "CLOSED"
}
```
Upgrade the status of a Request created by a Supplier user \(with access to Requests\) from SUBMITTED to CLOSED. When a Request created by a Supplier user is promoted, it contains an additional attribute, labeled Resolution Notes, in the response.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "GYI1FCGITARL4N6PFGI0"
    },
    "comment": "Request from our manufacturer. Moving from SUBMITTED to Closed",
    "status": "CLOSED",
    "resolutionCode": "As Designed",
    "resolutionNotes": "Please notifify Digi-Key we're closing their ECR-000045"
}
```


```
{
    "comment": "From Submitted to Promoted",
    "request": {
        "guid": "GYI1FCGITARL4N6PFGI0",
        "number": "ECR-000045"
    },
    "resolutionCode": "As Designed",
    "status": "CLOSED",
    "resolutionNotes": "Please notifify Digi-Key we're closing their ECR-000045"
}
```
