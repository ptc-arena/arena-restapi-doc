# GET Request Evaluator Groups


/settings/requests/evaluatorgroups



/settings/requests/evaluatorgroups/&lt;GUID&gt;

Returns Evaluator Groups available for Requests. Appending a GUID to the URL returns the routing with that GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
