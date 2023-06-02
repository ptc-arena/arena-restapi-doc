# GET Training Users
/trainingplans/&lt;GUID&gt;/users

Returns all the users \(trainees\) included within a Training Plan.

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
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
