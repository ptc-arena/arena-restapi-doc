# GET User Group Employees
/settings/usergroups/&lt;GUID&gt;/employees

Returns a list of employees in a specific User Group.

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
Get all employees in a User Group.

GET /settings/usergroups/&lt;GUID&gt;

```
{  
   "count":25,
   "results":[  
      {  
         "email":"johnsmith@company.com",
         "enabled":true,
         "firstName":"John",
         "fullName":"John Smith",
         "guid":"1J3MRHIIRYFYH0J258QX",
         "lastName":"Smith",
         "type":"EMPLOYEE"
      },
      {  
         "email":"vihaanluthra@company.com",
         "enabled":true,
         "firstName":"Vihaan",
         "fullName":"Vihaan Luthra",
         "guid":"8QATYOPPY5M5O7Q9C30O",
         "lastName":"Luthra",
         "type":"EMPLOYEE"
      },
      {  
         "email":"jchang@company.com",
         "enabled":true,
         "firstName":"Jason",
         "fullName":"Jason Chang",
         "guid":"7IJQWBOOA8J8O2D7C20PL",
         "lastName":"Chang",
         "type":"EMPLOYEE"
      },
      ...
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
