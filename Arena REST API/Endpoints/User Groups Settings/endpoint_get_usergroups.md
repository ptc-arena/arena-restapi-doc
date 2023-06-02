# GET User Groups
/settings/usergroups

Returns an array of   User Groups.

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
