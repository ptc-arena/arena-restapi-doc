# GET Request Evaluator Groups
/settings/requests/evaluatorgroups

/settings/requests/evaluatorgroups/&lt;GUID&gt;

Returns Evaluator Groups available for Requests. Appending a GUID to the URL returns the routing with that GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all request evaluator groups

GET /settings/requests/evaluatorgroups

```
{
    "count": 6,
    "results": [
        {
            "guid": "4M6P8L6XKN4L4N6P7X7E",
            "name": "Engineering plus Board Supplier"
        },
        {
            "guid": "3L5O7K5WJM3K3M5O5JDC",
            "name": "Product Enhancement"
        },
        {
            "guid": "SAUDW9UL8BS9SBUDUHW0",
            "name": "ECR Review Board"
        },
        ...
    ]
}
```
Get a request evaluator group with a specific GUID

GET /settings/requests/evaluatorgroups/GUID

```
{
    "guid": "SAUDW9UL8BS9SBUDUHW0",
    "name": "ECR Review Board"
}
```
