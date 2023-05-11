# GET Extract Run File


/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns an  object with a given GUID for a run with a given GUID of an extract with a given GUID. 

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
Get a file association with a specific GUID  for a Data Extract run



/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;

```
{  
   "downloadDateTime":null,
   "file":{  
      "author":null,
      "category":{},
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

