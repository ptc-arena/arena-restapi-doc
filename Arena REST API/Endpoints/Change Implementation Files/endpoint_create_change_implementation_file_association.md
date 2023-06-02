# POST Change Implementation Files View Add Existing File
/changes/&lt;GUID&gt;/implementationfiles

Associates an existing File Association object with the Implementation Files view of a  Change with a given GUID.

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
   "file":{  
      "guid":"WEYH0DYPCFYEXGJAW2JP"
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

## Sample Responses
Associate an existing file with the Implementation Files view of a specific Change.

/changes/&lt;GUID&gt;/implementationfiles

```
{
    "file": {
        "author": {
            "fullName": "George C Lewis"
        },
        "category": {
            "guid": "TBVEXAVM9CV5O7MTTUH9"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2011-06-02T19:30:28Z",
        "description": null,
        "edition": "1",
        "format": "pdf",
        "guid": "WEYH0DYPCFYEXGJAW2JP",
        "hasMarkup": false,
        "lastModifiedDateTime": "2011-06-02T19:30:28Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "application/pdf",
        "name": "ZIP-PWR-AC.pdf",
        "number": "FILE-000861",
        "private": false,
        "size": 120052,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "ZIP-PWR-AC"
    },
    "guid": "I0K3MZKBY1F3M5H1HVS5"
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
