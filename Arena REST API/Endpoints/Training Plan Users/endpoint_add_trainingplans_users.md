# POST Add Training Plan Users
/trainingplans/&lt;GUID&gt;/users

This endpoint adds a user to a Training Plan. In order to add a user to  a Training Plan, the user account executing the endpoint must be the Training Plan Manager.  

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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
