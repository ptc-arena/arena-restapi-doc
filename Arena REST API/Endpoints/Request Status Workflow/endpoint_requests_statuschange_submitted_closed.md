# POST Requests Status Change (Submitted to Closed)
/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Closed. This endpoint example is equivalent to closing a submitted Request within the browser-based application.

Note that Requests created by supplier users contain an additional property, labeled resolutionNotes, within their responses when closed.

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
Upgrade the status of a Request from SUBMITTED to CLOSED.

POST /requests/statuschanges

**Request** 

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
**Response** 

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

**Request** 

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
**Response** 

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
