# GET Training Plan User
/trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;

If the GET Training Plan Users endpoint is  appended with a valid guid, it returns the information of a specific user in a Training Plan.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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
