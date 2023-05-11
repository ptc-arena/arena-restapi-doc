# POST Training Plan Create


/trainingplans

This endpoint creates a Training Plan. In order to create a Training Plan, the user must be a Training Plan Manager. For Access Policies workspaces, user must also contain a policy that includes an Edit Training Summary rule.  

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
Create a Training Plan.



POST /trainingplans



```
{
    "numberSequencePrefix": {
        "value": "TRP-"
    },
    "name": "EveryHome Green Efficiency Initiative 2022",
    "description": "All employees must review Green 2022 Initiative",
    "manager": {
        "guid": "J1L4N0LCZ2J2L4N6F6ZL"
    },
    "daysToComplete": 30
}
```


```
{
    "creationDateTime": "2022-04-25T22:38:35Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "daysToComplete": 30,
    "description": "All employees must review Green 2022 Initiative",
    "guid": "FXH0JWH8VYF0J2L4NZB8",
    "manager": {
        "email": "tmakamuri@everyroadgps.com",
        "fullName": "Toshiro Makamuri",
        "guid": "J1L4N0LCZ2J2L4N6F6ZL"
    },
    "name": "EveryHome Green Efficiency Initiative 2022",
    "number": "TRP-000004",
    "status": "OPEN"
}
     
```
