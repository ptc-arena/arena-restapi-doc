# POST Requests Status Change (Submitted to Promoted)


/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Promoted. This endpoint example is equivalent to promoting a submitted Request within the browser\-based application.

Note that Requests created by supplier users contain an additional property, labeled resolutionNotes, within their responses when promoted.

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
Upgrade the status of a Request from SUBMITTED to PROMOTED.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "K2M5O1MD03ML4NJ32ZN1"
    },
    "comment": "From Submitted to Promoted",
    "status": "PROMOTED",
    "resolutionCode": "Approved [Immediate]"
}
```


```
{
    "comment": "From Submitted to Promoted",
    "request": {
        "guid": "K2M5O1MD03ML4NJ32ZN1",
        "number": "ECR-000009"
    },
    "resolutionCode": "Approved [Immediate]",
    "status": "PROMOTED"
}
```
Upgrade the status of a Request created by a Supplier user \(with access to Requests\) from SUBMITTED to PROMOTED. When a Request created by a Supplier user is promoted, it contains an additional attribute, labeled Resolution Notes, in the response.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "VDXGURVX8P7BUD7GLYB8"
    },
    "comment": "Request from our manufacturer. Moving from Submitted to Promoted",
    "status": "PROMOTED",
    "resolutionCode": "Approved [Immediate]",
    "resolutionNotes": "Please notifify Digi-Key we're promiting their ECR-000045"
}
```


```
{
    "comment": "From Submitted to Promoted",
    "request": {
        "guid": "VDXGURVX8P7BUD7GLYB8",
        "number": "ECR-000045"
    },
    "resolutionCode": "Approved [Immediate]",
    "status": "PROMOTED",
    "resolutionNotes": "Please notifify Digi-Key we're promiting their ECR-000045"
}
```
