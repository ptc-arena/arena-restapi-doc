# GET Users
/settings/users

/settings/users/&lt;GUID&gt;

Returns an array of Users matching the given search criteria. Appending a GUID to the URL returns the user with that GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all users where results should begin. All users before the offset in the search results are ignored. The default value is 0.   |
| limit  | integer  | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| firstName  | string  | The first name of the user  |
| lastName  | string  | The last name of the user  |
| fullName  | string  | The full \(first and last\) name of the user  |
| email  | valid email string  | The email address of the user  |
| type  | string  | The user type of the user. Values can be EMPLOYEE, PARTNER, BASIC_SUPPLIER, ADVANCED_SUPPLIER, or INTEGRATION.  |
| enabled  | boolean  | Whether or not a user account is enabled in the workspace. Values are True or False.  |

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
Get all users

GET /settings/users

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
         "type":"PARTNER"
      },
      {  
         "email":"jchang@trilbytech.com",
         "enabled":true,
         "firstName":"Jensen",
         "fullName":"Jensen Chang",
         "guid":"7IJQWBOOA8J8O2D7C20PL",
         "lastName":"Chang",
         "type":"ADVANCED_SUPPLIER"
      },
      ...
   ]
}

```
Get all users with the string *john*  in the fullName attribute

GET /settings/users?fullName=\*john

```
{  
   "count":2,
   "results":[  
      {  
         "email":"jparker@everyroadgps.com",
         "enabled":true,
         "firstName":"John",
         "fullName":"John Parker",
         "guid":"7P9SBJSSP6N6P8RATPM6",
         "lastName":"Parker",
         "type":"EMPLOYEE"
      },
      {  
         "email":"jwelles@everyroadgps.com",
         "enabled":true,
         "firstName":"John",
         "fullName":"John Welles",
         "guid":"8QATCKTTQ7O7Q9SBUQNX",
         "lastName":"Welles",
         "type":"EMPLOYEE"
      }
   ]
}
```
Get all advanced supplier users

GET /settings/users?type=ADVANCED_SUPPLIER

```
{  
   "count":2,
   "results":[  
      {  
         "email":"rmorgan@adaptive-boards.com",
         "enabled":true,
         "firstName":"Robert",
         "fullName":"Robert Morgan",
         "guid":"8QATCTCSO1I1K3M5OKFT",
         "lastName":"Morgan",
         "type":"ADVANCED_SUPPLIER"
      },
      {  
         "email":"htully@edgeelec.com",
         "enabled":true,
         "firstName":"Henry",
         "fullName":"Henry Tully",
         "guid":"9RBUDUDTP2J2L4N6PLGN",
         "lastName":"Tully",
         "type":"ADVANCED_SUPPLIER"
      }
   ]
}

```
Get a single user

GET /settings/users/N5P8R8R73GXGZI1K3YH7

```
{  
   "email":"eandersen@everyroadgps.com",
   "enabled":true,
   "firstName":"Ellen",
   "fullName":"Ellen Andersen",
   "guid":"N5P8R8R73GXGZI1K3YH7",
   "lastName":"Andersen",
   "type":"EMPLOYEE"
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
