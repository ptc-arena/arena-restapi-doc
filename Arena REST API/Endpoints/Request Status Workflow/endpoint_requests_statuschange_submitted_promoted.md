# POST Requests Status Change (Submitted to Promoted)
/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Promoted. This endpoint example is equivalent to promoting a submitted Request within the browser-based application.

Note that Requests created by supplier users contain an additional property, labeled resolutionNotes, within their responses when promoted.

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
Upgrade the status of a Request from SUBMITTED to PROMOTED.

POST /requests/statuschanges

**Request** 

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
**Response** 

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

**Request** 

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
**Response** 

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
