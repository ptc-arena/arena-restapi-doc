# GET Request Files View Association
/requests/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns a  specific Request-File association with a given GUID from the Files view of a specific Request with a given GUID.

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

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Request Files View  Association

GET &lt;url&gt;/requests/&lt;GUID&gt;/files/&lt;GUID&gt;

```
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
