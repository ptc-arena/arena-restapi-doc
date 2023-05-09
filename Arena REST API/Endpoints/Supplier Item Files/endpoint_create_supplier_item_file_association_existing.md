# POST Supplier Item File Add Existing 


/supplieritems/&lt;GUID&gt;/files

Associates an existing  object with a supplier item with a given GUID.

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

## Sample Request Body


```
{  
   "primary":false,
   "file":{  
      "guid":" GYI16WXX6DVYH0J2LEV8"
   }
}
```
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
Associate an existing file with a supplier item

```
{  
   "file":{  
      "author":{  
         "fullName":"John Parker"
      },
      "category":{  
         "guid":"R9TCH788HO7H0JV3RKSA"
      },
      "creationDateTime":"2011-06-02T19:30:28Z",
      "description":"Miniature Lamp Red/Green",
      "edition":"1",
      "format":"pdf",
      "guid":"5N7QVLMMV2L1K3ULBI65",
      "hasMarkup":false,
      "lastModifiedDateTime":"2011-06-02T19:30:28Z",
      "latest":true,
      "location":null,
      "locked":false,
      "mimeType":"application/pdf",
      "name":"7011X%20Series.pdf",
      "number":"FILE-000843",
      "private":false,
      "size":28847,
      "storageMethod":0,
      "storageMethodName":"FILE",
      "title":"Chicago Miniature Lamp 7011X Series Bicolor SMT LEDs"
   },
   "guid":"I0K38YZZ8FX1K3Z9LB19",
   "primary":false
}

```
An error is returned if:

* The GUID is not valid.

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
* a required metadata attribute is missing.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3001,
         "message":"The attribute \"edition\" is required."
      }
   ]
}
```
