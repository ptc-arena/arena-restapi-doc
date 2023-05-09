# PUT Supplier Item File Association Update


/supplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;

Updates information about  \(but not the content of\) an existing  with a given GUID associated with a supplier item with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
```
{  
   "primary":true
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json |   |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Update the details of a file associated with a supplier item



/supplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;

```
{  
   "file":{  
      "author":{  
         "fullName":"John Parker"
      },
      "category":{  
         "guid":"9RBUZPQQZ6PZI1DL92A2"
      },
      "creationDateTime":"2011-06-02T19:30:28Z",
      "description":"OrCAD native design file.",
      "edition":"1",
      "format":"DSN",
      "guid":"N5P8D344DK3J2LC3T0OM",
      "hasMarkup":false,
      "lastModifiedDateTime":"2011-06-02T19:30:28Z",
      "latest":true,
      "location":null,
      "locked":true,
      "mimeType":"application/octet-stream",
      "name":"OrcadCapture.DSN",
      "number":"FILE-000825",
      "private":false,
      "size":463360,
      "storageMethod":0,
      "storageMethodName":"FILE",
      "title":"OrCAD Schematic File"
   },
   "guid":"J1L49Z009GZBUD95YPP0",
   "primary":false
}
```
An error is returned if the GUID is not valid.

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
