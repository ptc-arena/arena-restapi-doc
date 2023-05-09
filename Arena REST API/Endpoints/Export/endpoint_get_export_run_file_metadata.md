# GET Export Run File Metadata


/exports/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns the metadata of an export file generated from an export run with a given GUID. 

For security reasons, only the user who ran the specific  export \(via the POST Export run\), can use this endpoint to obtain information about this specific export. Users who attempt to access the unique and specific export will encounter an error.

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
