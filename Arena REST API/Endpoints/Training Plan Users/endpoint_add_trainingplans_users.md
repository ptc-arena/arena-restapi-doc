# POST Add Training Plan Users
/trainingplans/&lt;GUID&gt;/users

This endpoint adds a user to a Training Plan. In order to add a user to  a Training Plan, the user account executing the endpoint must be the Training Plan Manager.  

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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

## Sample Requests and Responses
Add users to  a Training Plan.

POST /trainingplans/&lt;GUID&gt;/users

**Request** 

```
{
    "user": {
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "dueDate":"2022-11-28"
}
```
**Response** 

```
{
    "dueDate": "2022-11-28T07:59:59Z",
    "guid": "XFZI1EZQDGWFYH0JSIPU",
    "user": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
} 
```
