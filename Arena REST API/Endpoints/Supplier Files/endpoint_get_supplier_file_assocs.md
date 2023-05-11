# GET Supplier File Associations


/Supplier/&lt;GUID&gt;/files

Returns a collection of  objects belonging to a Supplier with a given GUID. To return a specific File association for an Item, append the GUID of the association.

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

## Sample Response Body
GET all files associated with a Supplier

GET /suppliers/VDXGZ7GGDUDUDRYLY132/files

```
{
    "count": 2,
    "results": [
        {
            "file": {
                "author": {
                    "fullName": "Yvette Keller"
                },
                "category": {
                    "guid": "7P9SBO90NQ9J2L0778VN"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-07-05T23:25:38Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "FXH0JWH8VYHXGZ2TFLZS",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-07-05T23:26:08Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "RoHS Certificate of Compliance 2.pdf",
                "number": "FILE-000942",
                "private": false,
                "size": 29846,
                "storageMethodName": "FILE",
                "title": "RoHS Certificate of Compliance"
            },
            "guid": "9RBUDQB2PS9H0J0S5FOB"
        },
        {
            "file": {
                "author": {
                    "fullName": "Kathy Davies"
                },
                "category": {
                    "guid": "CUEXGTE5SVEO7Q5CCD07"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-16T21:36:24Z",
                "description": "Rendered and color from 20-0002 base drawing",
                "edition": "2",
                "format": "png",
                "guid": "CUEXGTE5SVEUDWZQCIWW",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-16T21:36:24Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "image/x-png",
                "name": "EveryRoad Render4.png",
                "number": "FILE-000875",
                "private": false,
                "size": 74607,
                "storageMethodName": "FILE",
                "title": "EveryRoad GPS Car Navigation Unit - Model 300, Rendering"
            },
            "guid": "ASCVERC3QTAI1K1T6GP6"
        },
        ...
    ]
}
```
Request with bad GUID

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
