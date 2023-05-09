# PUT Training Plan Edit


/trainingplans/&lt;GUID&gt;

In order to edit a Training Plan, the user must be a Training Plan Manager within the workspace. If the user is a Training Plan Manager within the workspace but not the Training Plan Manager of this specific Training Plan, they can only use this endpoint to modify the Training Manager.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set description to null. Attribute must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID |

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
Edit a Training Plan.

/trainingplans/&lt;GUID&gt;



```
{
    "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
    "description": "All employees must review Green 2022 Initiative. Please contact your manager or HR if you have any questions.",
    "manager": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "daysToComplete": 36 
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
    "daysToComplete": 36,
    "description": "All employees must review Green 2022 Initiative. Please contact your manager or HR if you have any questions.",
    "guid": "FXH0JWH8VYF0J2L4NZB8",
    "manager": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
    "number": "TRP-000004",
    "status": "OPEN"
}
```


Set description to null.

PUT /trainingplans/&lt;GUID&gt;?setnull=true

```
{
    "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
    "description": null,
    "manager": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "daysToComplete": 36 
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
    "daysToComplete": 36,
    "description":null,
    "guid": "FXH0JWH8VYF0J2L4NZB8",
    "manager": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
    "number": "TRP-000004",
    "status": "OPEN"
}
```
User, who is a Training Manager but not the Training Manager of the specificied Training Plan, attempts to modify an attribute of the Training Plan other than the Training Manager attribute.

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
