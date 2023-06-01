# POST Change Implementation Files View Add Existing File
/changes/&lt;GUID&gt;/implementationfiles

Associates an existing File Association object with the Implementation Files view of a  Change with a given GUID.

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
      "guid":"WEYH0DYPCFYEXGJAW2JP"
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
