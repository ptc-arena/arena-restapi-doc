# POST Request File Markup Create


/requests/&lt;GUID&gt;/markupfiles

Creates a Request File Markup  object.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | multipart/form\-data<br> |   |

## Sample Request Body


```
{
    "file":{
        "guid":"Z43M5I3UHK3J2LN69BYY"
    }
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | determined by file type<br> | content type of file<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-FileGuid<br> | GUID string<br> | GUID for new file \- only when including content<br> |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
