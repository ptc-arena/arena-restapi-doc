# PUT Import Definition Edit
/imports/&lt;GUID&gt;

Edits the  import definition name and description. Import Engine endpoints are only supported in  Access Policies workspaces.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
* Edit the name or description of an import definition.

```
{
    "name": "Joe B's Personal Import Definition",
    "description": "Tailored Import for Sr. Developer J. Branson for the Skunkworks Project"
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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
