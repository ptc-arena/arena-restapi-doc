# POST Training Plan Create


/trainingplans

This endpoint creates a Training Plan. In order to create a Training Plan, the user must be a Training Plan Manager. For Access Policies workspaces, user must also contain a policy that includes an Edit Training Summary rule.  

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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
