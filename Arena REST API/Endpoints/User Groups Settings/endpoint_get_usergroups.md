# GET User Groups


/settings/usergroups

Returns an array of   User Groups.

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
Get all User Groups



GET /settings/usergroups

```
{
    "count": 6,
    "results": [
        {
            "assignability": [
                "ACCESS_POLICIES",
                "CHANGES",
                "QUALITY"
            ],
            "creationDateTime": "2020-12-02T06:30:40Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "Limited Workspace Access to Non-Admins",
            "enabled": true,
            "guid": "N5P8R4PG36CZI1K3MNJE",
            "lastModifiedDateTime": "2020-12-02T06:30:40Z",
            "modifiedBy": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Level 3 Partial Administrator"
        },
        {
            "assignability": [
                "CHANGES",
                "QUALITY"
            ],
            "creationDateTime": "2020-12-21T07:23:48Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": null,
            "enabled": true,
            "guid": "BTDWFSD4RU0N6P8RA955",
            "lastModifiedDateTime": "2020-12-21T07:23:48Z",
            "modifiedBy": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Quality Assurance"
        },
        {
            "assignability": [
                "ACCESS_POLICIES"
            ],
            "creationDateTime": "2020-12-21T17:56:29Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": null,
            "enabled": true,
}            "guid": "CUEXGTE5SV1O7Q9SBA60",
            "lastModifiedDateTime": "2020-12-22T19:31:49Z",
            "modifiedBy": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "*Level 3 Administrator -User Group"
        },
      ...
   ]
}

```
