# GET User Group Employee
/settings/usergroups/&lt;GUID&gt;/employees/&lt;GUID&gt;

Returns an employee user of a specific User Group.

This endpoint can only be used in Access Policies enabled workspaces.

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
Get an employee user of a specific User Group

GET /settings/usergroups/&lt;GUID&gt;/employees/&lt;GUID&gt;

```
{
  "user": {
    "email": "jappria@everyroadgps.com",
    "enabled": true,
    "firstName": "Joe",
    "fullName": "Joe Appria",
    "guid": "9RBU859BM3K3M5O7915S",
    "lastName": "Appria",
    "type": "EMPLOYEE"
  }
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
