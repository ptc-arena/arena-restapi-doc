# GET User Group Partner


/settings/usergroups/&lt;GUID&gt;/partners/&lt;GUID&gt;

Returns a Partner user of a User Group.

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
Get a specific Partner user of a specific User Group.



GET /settings/usergroups/&lt;GUID&gt;/partners/&lt;GUID&gt;

```
{
  "user": {
    "email": "joep@everyhomeconsulting.com",
    "enabled": true,
    "firstName": "Joe",
    "fullName": "Joe Patria",
    "guid": "K2M5JGKMXEVEXGZI1T4P",
    "lastName": "Partner",
    "type": "PARTNER"
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
