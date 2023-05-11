# GET User Group User


/settings/usergroups/&lt;GUID&gt;/users/&lt;GUID&gt;

Returns a specific user of a specific User Group.

This endpoint can only be used in Access Policies enabled workspaces.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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

## Sample Response Body
Get a user of a specific User Group.



GET /settings/usergroups/&lt;GUID&gt;/users/&lt;GUID&gt;

```
{
    "email": "jherrera@everyconsulting.com",
    "enabled": true,
    "firstName": "Judy",
    "fullName": "Judy Herrera",
    "guid": "XFZI1979WVCVEXGZI9IT",
    "lastName": "Herrera",
    "type": "PARTNER"
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
