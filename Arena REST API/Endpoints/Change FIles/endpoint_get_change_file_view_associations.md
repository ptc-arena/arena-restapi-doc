# GET Change Files View Associations


/changes/&lt;GUID&gt;/files

Returns a list of Files for a Change with a given GUID. 

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

## Sample Response Body
Change File  Associations

 

GET &lt;url&gt;/changes/&lt;GUID&gt;/files

```
{
    "count": 3,
    "results": [
        {
            "file": {
                "author": {
                    "fullName": "George C Lewis"
                },
                "category": {
                    "guid": "CUEXGTE5SVEO7Q5CCD07"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-02T19:30:28Z",
                "description": null,
                "edition": "1",
                "format": "jpg",
                "guid": "5N7Q9M7YLO7N6PSJ5BSL",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T21:48:39Z",
                "latest": true,
                "location": null,
                "locked": false,
                "mimeType": "image/jpeg",
                "name": "27005.jpg",
                "number": "FILE-000899",
                "private": false,
                "size": 9627,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "USB Mini Cable image"
            },
            "guid": "J1L4N0LCZ2JQ9SO87OGE"
        },
        {
            "file": {
                "author": {
                    "fullName": "George C Lewis"
                },
                "category": {
                    "guid": "CUEXGTE5SVEO7Q5CCD07"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-02T19:30:28Z",
                "description": "rework from ZIP-PWR-DC",
                "edition": "1",
                "format": "jpg",
                "guid": "ZH1K3G1SFI1H0JMDZ5MJ",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T21:53:42Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "image/jpeg",
                "name": "ZIP-PWR-DC.jpg",
                "number": "FILE-000864",
                "private": false,
                "size": 4480,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "USB to Car Power Adapter image"
            },
            "guid": "HZJ2LYJAX0HO7QM65MEH"
        },
        {
            "file": {
                "author": {
                    "fullName": "George C Lewis"
                },
                "category": {
                    "guid": "3L5O7K5WJM5FYHW334R7"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-02T19:30:28Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "K2M5O1MD03M2L47YKQ7D",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T19:30:28Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "USB to Car Power Adapter.pdf",
                "number": "FILE-000914",
                "private": false,
                "size": 41235,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "USB to Car Power Adapter"
            },
            "guid": "I0K3MZKBY1IP8RN76NF7"
        }
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
