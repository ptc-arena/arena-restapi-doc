# GET Training Users
/trainingplans/&lt;GUID&gt;/users

Returns all the users \(trainees\) included within a Training Plan.

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
Get the Training Plan Users  of  a Training Plan.

GET /trainingplans/&lt;GUID&gt;/users

```
{
    "count": 14,
    "results": [
        {
            "dueDate": "2016-12-21T07:59:59Z",
            "guid": "2K4N6J4VIL1K3M5OXNUH",
            "user": {
                "email": "ecanard@everyroadgps.com",
                "fullName": "Eleanor Canard",
                "guid": "1J3M5I3UHK1K3M5OXNUV"
            }
        },
        {
            "dueDate": null,
            "guid": "ZH1K3G1SFIYH0J2LUKR1",
            "user": {
                "email": "jdeckard@everyroadgps.com",
                "fullName": "James Deckard",
                "guid": "YG0J2F0REHYH0J2LUKR9"
            }
        },
        {
            "dueDate": "2017-04-14T06:59:59Z",
            "guid": "M4O7Q3OF25L4N6P8ADFD",
            "user": {
                "email": "test987789notreal@yahoo.com",
                "fullName": ";laksdf slakdf",
                "guid": "L3N6P2NE14L4N6P8ADFJ"
            }
        },
        ...
    ]
}
```
