# GET User Group Partners
/settings/usergroups/&lt;GUID&gt;/partners

Returns a list of Partners from a specific User Group.

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
Get partner users of a specific User Group.

GET /settings/usergroups/&lt;GUID&gt;/partners

```
{  
   "count":25,
   "results":[  
      {  
         "email":"johnsmith@evergreenconsulting.com",
         "enabled":true,
         "firstName":"John",
         "fullName":"John Smith",
         "guid":"1J3MRHIIRYFYH0J258QX",
         "lastName":"Smith",
         "type":"PARTNER"
      },
      {  
         "email":"mpatel@acmeconsulting.com",
         "enabled":true,
         "firstName":"Marie",
         "fullName":"Marie Patel",
         "guid":"8QATYOPPY5M5O7Q9C30O",
         "lastName":"Patel",
         "type":"PARTNER"
      },
      {  
         "email":"jchang@trilbytech.com",
         "enabled":true,
         "firstName":"Jensen",
         "fullName":"Jensen Chang",
         "guid":"7IJQWBOOA8J8O2D7C20PL",
         "lastName":"Chang",
         "type":"PARTNER"
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
