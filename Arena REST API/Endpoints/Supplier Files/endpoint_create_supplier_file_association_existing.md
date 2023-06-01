# POST Supplier File Add Existing
/suppliers/&lt;GUID&gt;/files

Associates an existing File Association object with an Supplier with a given GUID.

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
    "file": {
        "guid": "5N7Q9M7YLO7N6PSJ5BPC"
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
Associate an existing file with a Supplier.

/suppliers/&lt;GUID&gt;/files

```
{
    "file": {
        "author": {
            "fullName": "Helen Shaughnessy"
        },
        "category": {
            "guid": "3L5O7K5WJM5FYHW334R7"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2011-06-02T19:30:28Z",
        "description": "Datasheet for BASF Terluran GP-22 ABS",
        "edition": "1",
        "format": "pdf",
        "guid": "5N7Q9M7YLO7N6PSJ5BPC",
        "hasMarkup": false,
        "lastModifiedDateTime": "2011-06-02T19:30:28Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "application/pdf",
        "name": "BASF Terluran GP-22 (ABS) Datasheet.pdf",
        "number": "FILE-000888",
        "private": false,
        "size": 35086,
        "storageMethodName": "FILE",
        "title": "BASF Terluran GP-22 (ABS) Datasheet"
    },
    "guid": "BTDWFSD4RUBJ2L2U7HQD"
}
```
An error is returned if:
          
        

* The GUID is not valid.

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
