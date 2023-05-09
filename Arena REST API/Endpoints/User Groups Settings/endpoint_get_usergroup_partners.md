# GET User Group Partners


/settings/usergroups/&lt;GUID&gt;/partners

Returns a list of Partners from a specific User Group.

This endpoint can only be used in Access Policies enabled workspaces.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
