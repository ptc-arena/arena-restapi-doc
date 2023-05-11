# GET Change File Markup


/changes/&lt;GUID&gt;/markupfiles/&lt;GUID&gt;

Returns a Change File Markup object with a given GUID. This is the latest edition of the File.

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
Get a Change\-File association with a given GUID



GET &lt;url&gt;/changes/&lt;GUID&gt;/markupfiles/&lt;GUID&gt;

```
{
    "guid": "4M6P8L6XKN1O7QM65LS5",
    "markup": {
        "author": {
            "fullName": "ftp001"
        },
        "category": {
            "guid": "2K4N6J4VIL4EXGV223PR"
        },
        "creationDateTime": "2021-01-22T03:31:04Z",
        "format": "Web",
        "guid": "FXH0JWH8VYHXGZPWEY43",
        "lastModifiedDateTime": "2021-01-22T03:31:04Z",
        "location": "www.everyroadgps.com/Spring2021",
        "locked": false,
        "size": 0,
        "storageMethodName": "WEB",
        "title": "ftp001"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
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
