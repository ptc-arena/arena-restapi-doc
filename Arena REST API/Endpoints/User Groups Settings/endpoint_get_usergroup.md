# GET User Group


/settings/usergroups/&lt;GUID&gt;

Returns a specific User Group with a given GUID.

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
