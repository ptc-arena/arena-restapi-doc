# GET Extract Run Files


/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files

Returns  objects for a run with a given GUID of an extract with a given GUID. 
Appending a file association GUID returns the file association with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all file associations where results should begin. All runs before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of associations is 20. Can return up 400 associations.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| downloadDateTimeFrom<br> | string<br> | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)<br> |
| downloadDateTimeTo<br> | string<br> | Include runs downloaded after this date and time \(download date and time attributes refer to when the run was first downloaded, either by a user in the application or by the API\)<br> |

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
* \*If the file server is inaccessible, it may return a 400 status with no message.

