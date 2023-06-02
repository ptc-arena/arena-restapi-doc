# GET Files Search
/files

Returns a collection of  Compact Files  matching the given search criteria. The editions returned are the latest editions for each matching file. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all files where results should begin. All files before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. By default the maximum number of files is 20. Can return up 400 compact files.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| title  | string  | file title  |
| number  | string  | file number  |
| category.guid  | string  | category unique ID  |
| format  | string  | file format  |
| name  | string  | file name  |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

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
