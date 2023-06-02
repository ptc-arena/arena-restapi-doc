# GET Request File View Associations
/requests/&lt;GUID&gt;/files

Returns a list of files for a Request with a given GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Request Files View  Associations

GET &lt;url&gt;/requests/&lt;GUID&gt;/files

```
{
    "count": 5,
    "results": [
        {
            "file": {
                "author": {
                    "fullName": "Kathy Davies"
                },
                "category": {
                    "guid": "CUEXGTE5SVEO7Q5CCD07",
                    "name": "Image"
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
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "EveryRoad GPS Car Navigation Unit - Model 300, Rendering"
            },
            "guid": "3L5O7K5WJM39SBAEY0X0"
        },
        {
            "file": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "2K4N6J4VIL4EXGV223PR",
                    "name": "-uncategorized-"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-08-31T18:12:53Z",
                "description": "PDF output of CAD rendering for ERGPS 300 board.",
                "edition": "1",
                "format": "pdf",
                "guid": "Q8SBU7SJ69S8RAB9QGAJ",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-08-31T18:12:53Z",
                "latest": true,
                "location": null,
                "locked": false,
                "mimeType": "application/pdf",
                "name": "EveryRoad GPS Car Navigation Unit - Model 300, Rendering.pdf",
                "number": "FILE-000948",
                "private": false,
                "size": 8690,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "EveryRoad GPS Car Navigation Unit - Model 300, Rendering"
            },
            "guid": "4M6P8L6XKN4ATCBFZ1YG"
        },
        {
            "file": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "2K4N6J4VIL4EXGV223PR",
                    "name": "-uncategorized-"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-08-31T18:11:23Z",
                "description": "ERGPS MPI for assembling 300 PCBA.",
                "edition": "1",
                "format": "pdf",
                "guid": "ASCVERC3QTCSBUVTA0U1",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-08-31T18:11:23Z",
                "latest": true,
                "location": null,
                "locked": false,
                "mimeType": "application/pdf",
                "name": "MPI, ERGPS 300 Board.pdf",
                "number": "FILE-000947",
                "private": false,
                "size": 8690,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "MPI, ERGPS 300 Board"
            },
            "guid": "5N7Q9M7YLO5BUDCG02ZY"
        },
        ...
    ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
