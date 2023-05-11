# POST Requests Status Change (Closed to Promoted)


/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Closed to Promoted. This endpoint example is equivalent to closed Request within the browser\-based application.

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
Upgrade the status of a Request from CLOSED to PROMOTED.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "L3N6P2NE14NM5OK430OS"
    },
    "comment": "Reopening for further evaluation.",
    "status": "PROMOTED",
    "resolutionCode": "Approved [Future]"
}
```


```
{
    "comment": "Reopening for further evaluation.",
    "request": {
        "guid": "L3N6P2NE14NM5OK430OS",
        "number": "ECR-000010"
    },
    "resolutionCode": "Approved [Future]",
    "status": "PROMOTED"
}
```
Upgrade the status of a Request created by a Supplier user \(with access to Requests\) from CLOSED to PROMOTED. When a Request created by a Supplier user is promoted, it contains an additional attribute, labeled Resolution Notes, in the response.



POST /requests/statuschanges



```
{
    "request": {
        "guid": "DVFYC9DFQ7QYHV3DCJV6"
    },
    "comment": "Request from our manufacturer. Moving from Submitted to Promoted",
    "status": "PROMOTED",
    "resolutionCode": "Approved [Immediate]",
    "resolutionNotes": "Please notifify Digi-Key we're promoting their request after reconsidering"
}
```


```
{
    "comment": "From Submitted to Promoted",
    "request": {
        "guid": "DVFYC9DFQ7QYHV3DCJV6",
        "number": "ECR-000047"
    },
    "resolutionCode": "Approved [Immediate]",
    "status": "PROMOTED",
    "resolutionNotes": "Please notifify Digi-Key we're promoting their request after reconsidering"
}
```
