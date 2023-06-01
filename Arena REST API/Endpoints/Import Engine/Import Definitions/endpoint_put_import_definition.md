# PUT Import Definition Edit
/imports/&lt;GUID&gt;

Edits the  import definition name and description. Import Engine endpoints are only supported in  Access Policies workspaces.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
* Edit the name or description of an import definition.

```
{
    "name": "Joe B's Personal Import Definition",
    "description": "Tailored Import for Sr. Developer J. Branson for the Skunkworks Project"
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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
Edit the name or description of an import definition

```
{
    "name": "Joe B's Personal Import Definition",
    "description": "Tailored Import for Sr. Developer J. Branson for the Skunkworks Project",
    "resource": "ITEM_BOM",
    "mode": "REPLACE",
    "options": {
        "matchDuplicateParents": "ERROR",
        "removeValue": "[Remove Value]",
        "multiSelectDelimiter": ";",
        "checkRefDes": "CHECK",
        "stripWhiteSpace": "STRIP"
    },
    "number": 9,
    "creationDateTime": "2023-05-03T18:53:29Z",
    "creator": {
        "fullName": "Heidi Walker",
        "email": "hwalker@everyroadgps.com",
        "guid": "9RBUZOR8OFWFYH0JSIPJ"
    },
    "guid": "9RBUZOR8OFFI1K3M5N94"
}
```
