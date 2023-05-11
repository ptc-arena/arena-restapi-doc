# GET Request Administrators


/settings/requests/administrators

/settings/requests/administrators/&lt;GUID&gt;

Returns all the request administrators of a workspace. If appended with the guid of a specific administrator, returns the specific information of the specified request administrator.

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
Get the Request administrators of  a workspace.



GET /settings/requests/administrators

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
Get a specific Request Administrator with a given GUID.

GET /settings/requests/administrators/WEYHODYPCFWFYHOJSIPD

```
{
    "email": "hwalker@everyroadgps.com",
    "fullName": "Heidi Walker",
    "guid": "WEYH0DYPCFWFYH0JSIPD"
}
```
