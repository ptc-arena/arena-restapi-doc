# POST Requests Status Change (Closed to Promoted)


/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Closed to Promoted. This endpoint example is equivalent to closed Request within the browser\-based application.

Note that Requests created by supplier users contain an additional property, labeled resolutionNotes, within their responses when promoted.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
