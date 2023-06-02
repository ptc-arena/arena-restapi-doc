# POST Item File Add Existing
/items/&lt;GUID&gt;/files

Associates an existing File Association object with an item with a given GUID.

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

## Sample Request Body


```
{  
   "latestEditionAssociation":true,
   "primary":false,
   "file":{  
      "guid":" GYI16WXX6DVYH0J2LEV8"
   }
}
```
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
Associate an existing file with an item

/items/&lt;GUID&gt;/files

```
{  
   "file":{  
      "author":{  
         "fullName":"George Lewis"
      },
      "category":{  
         "guid":"K2L4N6PZI1DL92AR"
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
      "locked":false,
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
}
```
An error is returned if:

* The GUID is not valid.

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
* a required metadata attribute is missing.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3001,
      "message": "The attribute \"edition\" is required."
    }
  ]
}
```
