# POST Training Plans Files View Add Existing File


/trainingplans/&lt;GUID&gt;/files

Associates an existing file to the Files view of a Training Plan.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Sample Request Body
```
{
    "file": {
        "guid": "UCTQE5NGZI1AXZ3W"
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

## Sample Response Body
Training Plans Files View  Association



POST &lt;url&gt;/trainingplans/&lt;GUID&gt;/files

```
{
    "guid": "UCTQE5NGZI1AXZ3W",
    "latestEditionAssociation": true,
    "file": {
        "author": {
            "fullName": "Roy Stafford"
        },
        "category": {
            "guid": "EWGZDAEGR8R1K3J1LPP3",
            "name": "-uncategorized-"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2016-12-21T19:00:26Z",
        "description": null,
        "edition": "1",
        "format": "txt",
        "guid": "4M6P3046HYHXGZP3HMLL",
        "hasMarkup": false,
        "lastModifiedDateTime": "2016-12-21T19:00:26Z",
        "latest": false,
        "location": null,
        "locked": true,
        "mimeType": null,
        "name": "one.txt",
        "number": "FILE-007674",
        "private": false,
        "size": 631,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "one.txt"
    }
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
