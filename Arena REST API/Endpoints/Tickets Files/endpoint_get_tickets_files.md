# GET Ticket Files
/tickets/&lt;GUID&gt;/files

/tickets/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns a collection of  files associated with a Ticket   object. These are files located within the Files view of a Ticket. Appending a GUID to the URL returns the file with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all files associated with a  ticket

GET /tickets/&lt;GUID&gt;/files

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
                "creationDateTime": "2016-09-02T19:05:15Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "8QATCPA1ORAQ9SIYLDC6",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:05:15Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "020-00006 SOP, Risk Management.pdf",
                "number": "FILE-000971",
                "private": true,
                "size": 92123,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00006 SOP, Risk Management"
            },
            "guid": "N5P8R4PG36JO7Q9R58BB",
            "latestEditionAssociation": true
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
                "creationDateTime": "2016-09-02T19:05:53Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "J1L4N0LCZ2L1K3T9WOMD",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:05:53Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "020-00007 SOP, Supplier Quality Management.pdf",
                "number": "FILE-000973",
                "private": true,
                "size": 92171,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00007 SOP, Supplier Quality Management"
            },
            "guid": "P7RAT6RI58LQ9SBT7AD2",
            "latestEditionAssociation": true
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
                "creationDateTime": "2016-09-02T19:06:25Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "R9TCV8TK7AT9SB1H4WUE",
                "hasMarkup": false,
                "lastModifiedDateTime": "2016-09-02T19:06:25Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "020-00008 SOP, Production and Process Management.pdf",
                "number": "FILE-000975",
                "private": true,
                "size": 92192,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "020-00008 SOP, Production and Process Management"
            },
            "guid": "O6Q9S5QH47KP8RAS69CA",
            "latestEditionAssociation": true
        }
    ]
}
```
Get  a specific file with a specific GUID attached to a ticket of a specific GUID

GET /tickets/&lt;GUID&gt;/files/&lt;GUID&gt;

```
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
        "creationDateTime": "2016-09-02T19:05:15Z",
        "description": null,
        "edition": "1",
        "format": "pdf",
        "guid": "8QATCPA1ORAQ9SIYLDC6",
        "hasMarkup": false,
        "lastModifiedDateTime": "2016-09-02T19:05:15Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "application/pdf",
        "name": "020-00006 SOP, Risk Management.pdf",
        "number": "FILE-000971",
        "private": true,
        "size": 92123,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "020-00006 SOP, Risk Management"
    },
    "guid": "N5P8R4PG36JO7Q9R58BB",
    "latestEditionAssociation": true
}
```
