# POST Request Files View Add Existing File


/requests/&lt;GUID&gt;/files

Associates an existing  object with the Files view of a  Request with a given GUID.

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

## Sample Request Body


```
{
    "file": {
        "guid": "XFZI1EZQDGZFYHKBX3JI"
    }
}
```
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
Associate an existing file with a Request



/requests/&lt;GUID&gt;/files

```
{
    "file": {
        "author": {
            "fullName": "George C Lewis"
        },
        "category": {
            "guid": "CUEXGTE5SVEO7Q5CCD07",
            "name": "Image"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2011-06-02T19:30:28Z",
        "description": null,
        "edition": "1",
        "format": "jpg",
        "guid": "XFZI1EZQDGZFYHKBX3JI",
        "hasMarkup": false,
        "lastModifiedDateTime": "2011-06-02T19:30:28Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "image/jpeg",
        "name": "ZIP-PWR-AC.jpg",
        "number": "FILE-000926",
        "private": false,
        "size": 4494,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "Zip-LinQ US Adapter Image"
    },
    "guid": "HZJ2LYJAX0HN6PORLJZA"
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
