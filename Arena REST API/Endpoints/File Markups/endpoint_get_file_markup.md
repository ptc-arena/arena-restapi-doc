# GET File Markup


/files/&lt;GUID&gt;/markups/&lt;GUID&gt;

Returns a File Markup object with a given GUID. This is the latest edition of the File.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
Get a file with a given GUID



GET &lt;url&gt;/files/&lt;GUID&gt;/markups/&lt;GUID&gt;

```
{
    "guid": "XFZI1EZQDGUJ2LN69BYZ",
    "markup": {
        "author": {
            "fullName": "Tony Shaftoe"
        },
        "category": {
            "guid": "0I2L4H2TGJ2CVET001OY"
        },
        "creationDateTime": "2011-07-25T22:38:18Z",
        "format": "doc",
        "guid": "1J3M5I3UHK3J2LN69BYY",
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
    "request": {
        "guid": "Q8SBU7SJ69SRAT0L94BE",
        "number": "ECR-000001"
    },
    "reserved": false
}
```
Returns an error if a parameter is not a valid search attribute.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3019,
         "message":"The attribute \"edition\" is not searchable."
      }
   ]
}
```
