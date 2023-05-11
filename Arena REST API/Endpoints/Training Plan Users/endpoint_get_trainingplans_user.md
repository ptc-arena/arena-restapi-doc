# GET Training Plan User


/trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;

If the GET Training Plan Users endpoint is  appended with a valid guid, it returns the information of a specific user in a Training Plan.

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

## Sample Response Body
Get a specific Training Plan user with a given GUID.

GET /trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;

```
{
    "dueDate": null,
    "guid": "ZH1K3G1SFIYH0J2LUKR1",
    "user": {
        "email": "jdeckard@everyroadgps.com",
        "fullName": "James Deckard",
        "guid": "YG0J2F0REHYH0J2LUKR9"
    }
}
```
