# GET User Group Users
/settings/usergroups/&lt;GUID&gt;/users

Returns users of a specific User Group.

This endpoint can only be used in Access Policies enabled workspaces.

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
Get all users in a specific User Group.

GET /settings/usergroups/&lt;GUID&gt;/users

```
{
    "count": 2,
    "results": [
        {
            "email": "jwelles@everyroadgps.com",
            "enabled": false,
            "firstName": "Jackie",
            "fullName": "Jackie Welles",
            "guid": "GYI1KSQSFEVEXGZI007P",
            "lastName": "Welles",
            "type": "EMPLOYEE"
        },
        {
            "email": "mdeshawn@everyconsulting.com",
            "enabled": false,
            "firstName": "Marie",
            "fullName": "Marie DeShawn",
            "guid": "EWGZIQOQDCTCVEXGZOZL",
            "lastName": "DeShawn",
            "type": "PARTNER"
        }
    ]
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
