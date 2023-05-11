# GET Export Run File Metadata


/exports/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns the metadata of an export file generated from an export run with a given GUID. 

For security reasons, only the user who ran the specific  export \(via the POST Export run\), can use this endpoint to obtain information about this specific export. Users who attempt to access the unique and specific export will encounter an error.

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

## Sample Response Body
Get the metadata of an export run.



GET /exports/&lt;export definition GUID&gt;/runs/&lt;export run GUID&gt;/files/&lt;export file GUID&gt;

```
{  
   "author": null
   "category: {}
   "creationDateTime":"2020-03-09T21:18:46Z",  
   "description": null,
   "edition": null,
   "format": null,
   "guid": "VDXGZX0BEXDWF5CV9RE",
   "hasMarkup": false,
   "lastModifiedDateTime": "2020-03-09T21:18.46Z"
   "latest": false,
   "location": null,
   "locked": true,
   "mimeType": "application/zip",
   "name": "Model 300 Export Results.zip",
   "number": null,
   "private": false,
   "size": 1419,
   "storageMethodName": "FILE",
   "title": null    
}
```
request made by a user who did not initiate the export run

```
{  
   "status":403,
   "errors":[  
      {  
         "code":3024,
         "message":"Either you do not have privileges to access the requested data or it does not exist."
      }
   ]
}
```
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
