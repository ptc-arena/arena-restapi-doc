# GET Files Search


/files

Returns a collection of    matching the given search criteria. The editions returned are the latest editions for each matching file. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all files where results should begin. All files before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of files is 20. Can return up 400 compact files.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| title<br> | string<br> | file title<br> |
| number<br> | string<br> | file number<br> |
| category.guid<br> | string<br> | category unique ID<br> |
| format<br> | string<br> | file format<br> |
| name<br> | string<br> | file name<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

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
Get PDF format files whose title begins with the string "everyroad"



GET &lt;url&gt;/files?title=everyroad\*&format=pdf 

```
{  
   "count":20,
   "results":[  
      {  
         "category":{  
            "guid":"M4O7QY5R7FY8RATAYXNX",
            "name":"Design Drawing",
            "path":"File\\Engineering\\Design Drawing" 
         },
         "checkedOut": false,
         "corrected": false,
         "creationDateTime":"2006-09-21T21:51:11Z",
         "edition":"01",
         "format":"pdf",
         "guid":"ASCVEMTFV3M2L4NWYCGO",
         "name":"everyroad-500-mpi-1.pdf",
         "number":"FILE-000172",
         "title":"500 board image for MPI"
      },
      {  
         "category":{  
            "guid":"M4O7QY5R7FY8RATAYXNX",
            "name":"Design Drawing",
            "path":"File\\Engineering\\Design Drawing" 
         },
         "checkedOut": false,
         "creationDateTime":"2006-09-21T20:49:34Z",
         "edition":"01",
         "format":"pdf",
         "guid":"J1L4NV2O4CVBUDW57LPY",
         "name":"everyroad-500-footprint.pdf",
         "number":"FILE-000145",
         "title":"500 board footprint"
      },
      ...
   ]
}


```
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
   "chekedOut": false,
   "corrected": true,
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
