# POST Change Files View Add Existing File
/changes/&lt;GUID&gt;/files

Associates an existing File Association object with the Files view of a  Change with a given GUID.

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
   "file":{  
      "guid":"VDXGZCXOBEXDWFI9V1ID"
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

## Sample Responses
Associate an existing file with a Change

/changes/&lt;GUID&gt;/files

```
{
    "file": {
        "author": {
            "fullName": "Bret D Lobree"
        },
        "category": {
            "guid": "3L5O7K5WJM5FYHW334R7"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2011-06-02T19:30:28Z",
        "description": "COMPACT PLCC SOCKETS Surface Mount",
        "edition": "1",
        "format": "pdf",
        "guid": "VDXGZCXOBEXDWFI9V1ID",
        "hasMarkup": false,
        "lastModifiedDateTime": "2011-06-02T19:30:28Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "application/pdf",
        "name": "095.pdf",
        "number": "FILE-000860",
        "private": false,
        "size": 154507,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "Mill-Max Series 540"
    },
    "guid": "L3N6P2NE14LSBUQA9QHP"
}
```
An error is returned if the GUID is not valid.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
