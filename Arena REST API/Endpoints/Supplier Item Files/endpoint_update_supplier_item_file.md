# PUT Supplier Item File Association Update
/supplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;

Updates information about  \(but not the content of\) an existing File with a given GUID associated with a supplier item with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "primary":true
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> |   |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
