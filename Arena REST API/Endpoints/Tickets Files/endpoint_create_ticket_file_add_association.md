# POST Tickets Files View Add Existing File
/tickets/&lt;GUID&gt;/files

Associates an existing file to the Files view of a ticket.

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

## Sample Request Body
```
{
    "file": {
        "guid": "8QATCPA1ORAQ9SIYLDC6"
    }
}
```
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
Tickets Files View  Association

POST &lt;url&gt;/tickets/&lt;GUID&gt;/files

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
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
