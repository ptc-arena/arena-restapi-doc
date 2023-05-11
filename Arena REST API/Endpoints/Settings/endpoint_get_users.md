# GET Users


/settings/users



/settings/users/&lt;GUID&gt;

Returns an array of  matching the given search criteria. Appending a GUID to the URL returns the user with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all users where results should begin. All users before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| firstName<br> | string<br> | The first name of the user<br> |
| lastName<br> | string<br> | The last name of the user<br> |
| fullName<br> | string<br> | The full \(first and last\) name of the user<br> |
| email<br> | valid email string<br> | The email address of the user<br> |
| type<br> | string<br> | The user type of the user. Values can be EMPLOYEE, PARTNER, BASIC_SUPPLIER, ADVANCED_SUPPLIER, or INTEGRATION.<br> |
| enabled<br> | boolean<br> | Whether or not a user account is enabled in the workspace. Values are True or False.<br> |

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
Get all users with the string  in the fullName attribute



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
