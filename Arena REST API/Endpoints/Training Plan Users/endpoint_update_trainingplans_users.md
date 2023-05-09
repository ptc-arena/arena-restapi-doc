# PUT Update Training Plan User


/trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;

In order to modify  a user in a Training Plan, the user must be a Training Plan Manager within the workspace. Currently, the only modification to a user in a Training Plan supported is the ability to change due date of  a user's training assignments..

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
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
Edit the due date of a user's training assignment in a specific Training Plan.

/trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;



```
{
    "dueDate": "2023-01-30"
}

```


```
{
    "dueDate": "2023-01-30T07:59:59Z",
    "guid": "K2M5O1MD03J2L4N6F6Z5",
    "user": {
        "email": "tmakamuri@everyroadgps.com",
        "fullName": "Toshiro Makamuri",
        "guid": "J1L4N0LCZ2J2L4N6F6ZL"
    }
}
```
User, who is not the Training Manager of the specificied Training Plan, attempts to modify a user's training assignment due date.

```
{
    "status": 400,
    "errors": [
        {
            "code": 4217,
            "message": "Only the assigned training manager for this training plan can perform this action."
        }
    ]
}
```
