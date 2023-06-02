# GET User Group Employees
/settings/usergroups/&lt;GUID&gt;/employees

Returns a list of employees in a specific User Group.

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
