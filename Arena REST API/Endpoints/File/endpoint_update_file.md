# PUT File Summary Update
/files/&lt;GUID&gt;

Updates a  File object.

Also supports updating File storageMethodName from FILE, FTP, WEB, or PLACE_HOLDER to FTP, WEB, or PLACE_HOLDER. This update can only be performed on unlocked Files.

Updating storageMethodName to  FTP, WEB, or PLACE_HOLDER also requires including the attribute location.

This endpoint does not support updating the storageMethodName from FTP, WEB, or PLACE_HOLDER to FILE. This requires a POST call. See POST File  Update.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Set Null

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| setnull  |   | Append the URL with setnull=true to set description or format to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.  |

## Sample Request Body


This example shows all editable attributes.

```
{  
   "author":{  
      "fullName":"John Parker"
   },
   "category":{  
      "guid":"EWGZDAEGR8R1K3J1LPP3"
   },
   "description":"Assembly Instructions",
   "edition":"B-1",
   "format":"PDF",
   "title":"Assembly Instructions for 324-0263"
}
```
## Sample Request Body - Updating storageMethodName
In this example, the existing File  has a storageMethodName of FILE and through the PUT endpoint we're updating it to storageMethodName of WEB.

```
{
  "author":{
    "fullName":"George Lewis"
  },
  "category":{
    "guid":"7P9S6379K1KUDWCUEIJG"
  },
  "description":"Arena Solutions Corporate Link",
  "edition":"1",
  "format":"url",
  "location":"https://www.arenasolutions.com/345634.html",
  "storageMethodName": "WEB",
  "private":false,
  "title":"Link to Assembly Instructions for 324-0263"
}
```
## Sample Request Body - Set to Null
In this example, a File attribute is set to null.

PUT /files/&lt;GUID&gt;?setnull=true

```
{  
   "format":null
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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
Update the details of a file

files/&lt;GUID&gt;

```
{  
   "author":{  
      "fullName":"John Parker"
   },
   "category":{  
      "guid":"EWGZDAEGR8R1K3J1LPP3"
   },
   "creationDateTime":"2013-03-14T23:19:28Z",
   "description":"Assembly Instructions",
   "edition":"B-1",
   "format":"PDF",
   "guid":"GYI16WXX6DVYH0J2LEVZ ",
   "hasMarkup":false,
   "lastModifiedDateTime":"20170123132756",
   "latest":true,
   "location":null,
   "locked":false,
   "mimeType":null,
   "name":"324-0263-a.pdf",
   "number":"FILE-000544",
   "private":false,
   "size":125083,
   "storageMethodName":"FILE",
   "title":"Assembly Instructions for 324-0263"
}
```
Updates the storageMethodName of a File from FILE to WEB.

```
{
  "author":{
    "fullName":"George Lewis"
  },
  "category":{
    "guid":"7P9S6379K1KUDWCUEIJG"
    "name":"
    "path":"
  },
  "creationDateTime": "2020-08-28T17:40:08Z",
  "description":"Arena Solutions Corporate Link",
  "edition":"1",
  "format":"url",
  "guid": "9RBU859BM3M2L4UF7BRK",
  "hasMarkup": false,
  "lastModifiedDateTime": "2020-08-29T12:27:84Z",
  "latest": true,
  "location":"https://www.arenasolutions.com/345634.html",
  "locked": false,
  "mimeType": null,
  "name": null,
  "number": "FILE-045893",
  "private": false,
  "size": 0,
  "storageMethodName": "WEB",
  "private":false,
  "title":"Link to Assembly Instructions for 324-0263"
}
```
Sets a file attribute to null.

PUT /files/&lt;GUID&gt;?setnull=true

```
{  
   "author":{  
      "fullName":"John Parker"
   },
   "category":{  
      "guid":"EWGZDAEGR8R1K3J1LPP3"
   },
   "creationDateTime":"2013-03-14T23:19:28Z",
   "description":"Assembly Instructions",
   "edition":"B-1",
   "format":null,
   "guid":"GYI16WXX6DVYH0J2LEVZ ",
   "hasMarkup":false,
   "lastModifiedDateTime":"20170123132756",
   "latest":true,
   "location":null,
   "locked":false,
   "mimeType":null,
   "name":"324-0263-a.pdf",
   "number":"FILE-000544",
   "private":false,
   "size":125083,
   "storageMethodName":"FILE",
   "title":"Assembly Instructions for 324-0263"
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"EWGZDAEGR8R1K3J1LPP3\" is not valid."
      }
   ]
}
```
