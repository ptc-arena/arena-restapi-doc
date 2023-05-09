# GET Supplier File Association


/suppliers/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns a  Supplier File association object with a given GUID belonging to an item with a given GUID. 

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
GET a specific file associated with a Supplier.

GET /suppliers/QDXGZ7GGDUDUDRYLY138/files/9L5O7FOOL2LXGZIY5X2Z

```
{  
   "file":{  
      "author":{  
         "fullName":"George C Lewis"
      },
      "category":{  
         "guid":"Z9O7QY5R7FY8RATAYWBF",
         "name":"Design Drawing",
         "path":"File\\Engineering\\Model File" 
      },
      "checkedOut": false,
      "creationDateTime":"2011-02-11T17:54:40Z",
      "description":null,
      "edition":"1",
      "format":"pdf",
      "guid":"VDXGZ7GGDUDTCVENSKLI",
      "hasMarkup":false,
      "lastModifiedDateTime":"2011-02-12T01:54:40Z",
      "latest":true,
      "location":null,
      "locked":true,
      "mimeType":"application/pdf",
      "name":"EveryRoad PCBA Model 500.pdf",
      "number":"FILE-000059",
      "private":false,
      "size":416233,
      "smartLink":"https://files.sand.bom.com:8041/p/ Q7Q6-P8RA-QO30-O53P-SCDY-CYF3",
      "storageMethod":0,
      "storageMethodName":"FILE",
      "title":"EveryRoad PCBA Model 500"
   },
   "guid":"3L5O7FOOL2LXGZIY5X2M",
   "latestEditionAssociation":true,
   "primary":true
}
```
Produces an error if the GUID is not valid.

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
