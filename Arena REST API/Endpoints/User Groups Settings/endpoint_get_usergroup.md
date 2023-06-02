# GET User Group
/settings/usergroups/&lt;GUID&gt;

Returns a specific User Group with a given GUID.

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
Get a specific User Group

GET /settings/usergroups/&lt;GUID&gt;

```
{
  "guid": "L3N6KHLNYFY8RAQ8SWYT",
  "name": "Quality Assurance",
  "description": "QA Team",
  "enabled": true,
  "creator": {
    "email": "dsullivan@arenasolutions.com",
    "fullName": "Don Sullivan",
    "guid": "K2M5JGKMXEVEXGZI1T4P"
  },
  "creationDateTime": "2008-03-07T19:58:40Z",
  "lastModifiedDateTime": "2017-06-18T22:52:40Z",
  "modifiedBy": {
    "email": "dsullivan@arenasolutions.com",
    "fullName": "Don Sullivan",
    "guid": "K2M5JGKMXEVEXGZI1T4P"
  },
  "assignability": ["QUALITY", "CHANGES", "POLICIES"]
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
