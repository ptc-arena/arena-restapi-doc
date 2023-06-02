# GET Extract Run Files
/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files

Returns Extract Run File Association objects for a run with a given GUID of an extract with a given GUID. <br>Appending a file association GUID returns the file association with that GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all file associations where results should begin. All runs before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. By default the maximum number of associations is 20. Can return up 400 associations.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| downloadDateTimeFrom  | string  | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)   |
| downloadDateTimeTo  | string  | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)   |

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

## Sample Response Body
Get all file associations for a Data Extract run

/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files

```
{  
   "count":1,
   "results":[  
      {  
         "downloadDateTime":null,
         "file":{  
            "author":null,
            "category":{  

            },
            "creationDateTime":"2015-08-17T16:48:30Z",
            "description":null,
            "edition":null,
            "format":"zip",
            "guid":"VDXGURVX8P8O7QH2PO36",
            "hasMarkup":false,
            "lastModifiedDateTime":"2015-08-17T16:48:30Z",
            "latest":false,
            "location":null,
            "mimeType":null,
            "name":"Extract_20150817_164826Z_FXH0EBFHS9SK3M5O7QS1.zip",
            "number":null,
            "private":false,
            "size":8989,
            "storageMethod":0,
            "title":null
         },
         "guid":"3L5O2Z35GXG6P8R88MYW"
      }
   ]
}
```
An error is returned if:

* the GUID is not valid.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
* An error is thrown by the file server

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3017,
         "message":"The file with guid \"7P60AQ9P8RAS7F6J\" cannot be downloaded at this time."
      }
   ]
}
```
* *If the file server is inaccessible, it may return a 400 status with no message.

