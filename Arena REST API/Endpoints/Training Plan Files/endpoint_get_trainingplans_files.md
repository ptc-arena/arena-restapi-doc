# GET Training Plan Files


/trainingplans/&lt;GUID&gt;/files

Returns all the files associated within a specific Training Plan. Using the browser\-based application as a point of comparison, this endpoint returns the files located within the Files view of a specific Training Plan.

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
Get the files within the Files view  of  a Training Plan.



GET /trainingplans/&lt;GUID&gt;/files

```
{
    "count": 3,
    "results": [
        {
            "file": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "2K4N6J4VIL4EXGV223PR",
                    "name": "-uncategorized-"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2016-09-02T19:00:27Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "L3N6P2NE14N3M5VBYQQ3",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:00:27Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "020-00001 SOP, Document Control Management.pdf",
                "number": "FILE-000961",
                "private": true,
                "size": 92146,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00001 SOP, Document Control Management"
            },
            "guid": "HZJ2LYJAX0DSBUDVA6PX"
        },
        {
            "file": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "2K4N6J4VIL4EXGV223PR",
                    "name": "-uncategorized-"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2016-09-02T19:01:26Z",
                "description": null,
                "edition": "1",
                "format": "docx",
                "guid": "WEYH0DYPCFYEXG6M911I",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:01:26Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                "name": "020-00002 SOP, Change Control.docx",
                "number": "FILE-000964",
                "private": true,
                "size": 35440,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00002 SOP, Change Control"
            },
            "guid": "I0K3MZKBY1ETCVEWB7QK"
        },
        {
            "file": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "2K4N6J4VIL4EXGV223PR",
                    "name": "-uncategorized-"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2016-09-02T19:02:08Z",
                "description": null,
                "edition": "1",
                "format": "docx",
                "guid": "4M6P8L6XKN6M5OEUH99C",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:02:08Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                "name": "020-00003 SOP, Control of Records.docx",
                "number": "FILE-000966",
                "private": true,
                "size": 35450,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00003 SOP, Control of Records"
            },
            "guid": "J1L4N0LCZ2FUDWFXC8RA"
        }
    ]
}
```
