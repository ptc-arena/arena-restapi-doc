# GET File Editions


/files/&lt;GUID&gt;/editions

Returns a collection of   objects for a File with a given GUID. 

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
```
{  
   "count":3,
   "results":[  
      {  
         "author":{  
            "fullName":"Heidi Walker"
         },
         "category":{  
            "guid":"D3O7QY5R7FY8RATAYXNX",
            "name":"Design Drawing",
            "path":"File\\Engineering\\Instructions" 
         },
         "checkedOut": false,
         "creationDateTime":"2016-02-01T22:28:10Z",
         "description":"Assembly instructions",
         "edition":"3",
         "format":"pdf",
         "guid":"9ASCVEMTFV3M2L4NWYCGO",
         "hasMarkup":false,
         "lastModifiedDateTime":"2016-02-01T22:28:10Z",
         "latest":true,
         "location":null,
         "locked":true,
         "mimeType":"text/plain",
         "name":"everyroad-500-schematic.pdf",
         "number":"FILE-000593",
         "private":false,
         "size":14081,
         "storageMethodName":"FILE",
         "title":"500 board schematic"
      },
      ...
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
