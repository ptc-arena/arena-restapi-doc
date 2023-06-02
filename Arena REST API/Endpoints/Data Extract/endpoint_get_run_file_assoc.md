# GET Extract Run File
/extracts/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns an Extract Run File Association object with a given GUID for a run with a given GUID of an extract with a given GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
* *If the file server is inaccessible, it may return a 400 status with no message.

