# GET Request File Markup


/requests/&lt;GUID&gt;/markupfiles/&lt;GUID&gt;

Returns a Request File Markup object with a given GUID. This is the latest edition of the File.

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
Get a Requests file with a given GUID



GET &lt;url&gt;/requests/&lt;GUID&gt;/markupfiles/&lt;GUID&gt;

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
