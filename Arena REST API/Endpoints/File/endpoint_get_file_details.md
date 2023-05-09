# GET File Summary


/files/&lt;GUID&gt;

Returns a  object with a given GUID. This is the latest edition of the File.

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
