# GET File Summary


/files/&lt;GUID&gt;

Returns a  object with a given GUID. This is the latest edition of the File.

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

## Sample Responses
Get a file with a given GUID



GET &lt;url&gt;/files/&lt;GUID&gt;

```
{  
   "author":{  
      "fullName":"Heidi Walker"
   },
   "category":{  
      "guid":"M4O7QY5R7FY8RATAYXNX",
      "name":"Design Drawing",
      "path":"File\\Engineering\\Design Drawing" 
   },
   "checkedOut": false,
   "corrected": false,
   "creationDateTime":"2006-09-21T20:49:34Z",
   "description":"500 Board MPI",
   "edition":"01",
   "format":"pdf",
   "guid":"P7RAT18UAI1H0J2BDRVF",
   "hasMarkup":false,
   "lastModifiedDateTime":"2006-09-21T20:49:34Z",
   "latest":true,
   "location":null,
   "locked":false,
   "mimeType":"application/pdf",
   "name":"308-0345-a.pdf",
   "number":"FILE-000151",
   "private":false,
   "size":82121,
   "storageMethodName":"FILE",
   "title":"308-0345-a"
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
