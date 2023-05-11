# GET Item File Associations


/items/&lt;GUID&gt;/files

Returns a collection of  objects belonging to an item with a given GUID. To return a specific File association for an Item, append the GUID of the association.

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
