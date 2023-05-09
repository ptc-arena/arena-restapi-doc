# POST Supplier File Add Existing


/suppliers/&lt;GUID&gt;/files

Associates an existing  object with an Supplier with a given GUID.

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
        "guid": "5N7Q9M7YLO7N6PSJ5BPC"
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
