# POST Tickets Files View Add Existing File
/tickets/&lt;GUID&gt;/files

Associates an existing file to the Files view of a ticket.

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

## Sample Request Body
```
{
    "file": {
        "guid": "8QATCPA1ORAQ9SIYLDC6"
    }
}
```
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
