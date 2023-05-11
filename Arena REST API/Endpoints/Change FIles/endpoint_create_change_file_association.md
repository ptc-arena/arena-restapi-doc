# POST Change Files View Add Existing File


/changes/&lt;GUID&gt;/files

Associates an existing  object with the Files view of a  Change with a given GUID.

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

## Sample Request Body


```
{  
   "file":{  
      "guid":"VDXGZCXOBEXDWFI9V1ID"
   }
}
```
## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
