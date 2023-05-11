# POST Request Files View Add Existing File


/requests/&lt;GUID&gt;/files

Associates an existing  object with the Files view of a  Request with a given GUID.

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
    "file": {
        "guid": "XFZI1EZQDGZFYHKBX3JI"
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
