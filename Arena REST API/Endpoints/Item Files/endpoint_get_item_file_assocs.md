# GET Item File Associations


/items/&lt;GUID&gt;/files

Returns a collection of  objects belonging to an item with a given GUID. To return a specific File association for an Item, append the GUID of the association.

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
GET all files associated with an item

GET /items/VDXGZ7GGDUDUDRYLY132/files

```
{  
   "count":4,
   "results":[  
      {  
         "file":{  
            "author":{  
               "fullName":"George Lewis"
            },
            "category":{  
               "guid":"Q5O7QY5R7FY8RATAYXNX",
               "name":"Design Drawing",
               "path":"File\\Engineering\\Schematic" 
            },
            "checkedOut": false,
            "corrected": false,
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
         "guid":"N5O7Q9SYH0W6I7OW",
         "latestEditionAssociation":true,
         "primary":false
      },
      ...
   ]
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
