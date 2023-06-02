# GET Change Administrators
/settings/changes/administrators

/settings/changes/administrators/&lt;GUID&gt;

Returns all the change administrators of a workspace. If appended with a valid guid, it returns the information of that specific change administrator.

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
Get the Change Administrators of  a workspace.

GET /settings/changes/administrators

```
{
    "count": 3,
    "results": [
        {
            "email": "tmakamuri@everyroadgps.com",
            "fullName": "Toshiro Makamuri",
            "guid": "J1L4N0LCZ2J2L4N6F6ZL"
        },
        {
            "email": "jparker@everyroadgps.com",
            "fullName": "John Parker",
            "guid": "XFZI1EZQDGXGZI1KTJQ2"
        },
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        }
    ]
}
```
Get a specific Change Administrator with a given GUID.

GET /settings/changes/administrators/WEYHODYPCFWFYHOJSIPD

```
{
    "email": "hwalker@everyroadgps.com",
    "fullName": "Heidi Walker",
    "guid": "WEYH0DYPCFWFYH0JSIPD"
}
```
