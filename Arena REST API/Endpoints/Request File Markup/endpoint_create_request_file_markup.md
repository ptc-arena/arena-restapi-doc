# POST Request File Markup Create
/requests/&lt;GUID&gt;/markupfiles

Creates a Request File Markup File object.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | multipart/form-data  |   |

## Sample Request Body


```
{
    "file":{
        "guid":"Z43M5I3UHK3J2LN69BYY"
    }
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
| Content-Type  | determined by file type  | content type of file  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-FileGuid  | GUID string  | GUID for new file - only when including content  |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Responses
* When associating a File Markup to a Request:

```
{
    "guid": "7B4E2M7YLO2P8RN76MT6",
    "markup": {
        "author": {
            "fullName": "Tony Shaftoe"
        },
        "category": {
            "guid": "0I2L4H2TGJ2CVET001OY"
        },
        "creationDateTime": "2011-07-25T22:38:18Z",
        "format": "doc",
        "guid": "Z43M5I3UHK3J2LN69BYY",
        "lastModifiedDateTime": "2011-07-25T22:38:18Z",
        "locked": true,
        "mimeType": "application/msword",
        "name": "mount-instructions-07-25-2011.doc",
        "size": 27136,
        "storageMethodName": "FILE",
        "title": "mount-instructions-07-25-2011"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": false
}
```
Returns an error  if a required metadata attribute is missing.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3001,
         "message":"The attribute \"edition\" is required."
      }
   ]
}
```
