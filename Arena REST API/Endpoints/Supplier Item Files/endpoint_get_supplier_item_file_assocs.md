# GET Supplier Item File Associations


/supplieritems/&lt;GUID&gt;/files

Returns an array of  objects belonging to a supplier item with a given GUID. 

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
Get file associations for a given supplier item



/supplieritems/&lt;GUID&gt;/files

```
{  
   "count":2,
   "results":[  
      {  
         "file":{  
            "author":{  
               "fullName":"Rachael Borg"
            },
            "category":{  
               "guid":"I0K38YZZ8FY8RAMUIBIK",
               "name":"Design Drawing",
               "path":"File\\Engineering\\Drawings" 
            },
            "checkedOut": false,            
            "corrected": false,
            "creationDateTime":"2011-06-02T19:30:28Z",
            "description":null,
            "edition":"1",
            "format":"doc",
            "guid":"BTDW1RSS18R7Q90RHOD5",
            "hasMarkup":false,
            "lastModifiedDateTime":"2011-06-02T19:30:28Z",
            "latest":true,
            "location":null,
            "locked":false,
            "mimeType":null,
            "name":"7011X1-5.doc",
            "number":"FILE-000814",
            "private":false,
            "size":31232,
            "storageMethod":0,
            "storageMethodName":"FILE",
            "title":"7011X1-5"
         },
         "guid":"FXH05VWW5CUYH0W6I8ZD",
         "primary":true
      },
      {  
         "file":{  
            "author":{  
               "fullName":"John Parker"
            },
            "category":{  
               "guid":"R9TCH788HO7H0JV3RKSA",
               "name":"Design Drawing",
               "path":"File\\Engineering\\Product Requirements Doc" 
            },
            "checkedOut": false, 
            "creationDateTime":"2011-06-02T19:30:28Z",
            "corrected": false,
            "description":"Miniature Lamp Red/Green",
            "edition":"1",
            "format":"pdf",
            "guid":"5N7QVLMMV2L1K3ULBI65",
            "hasMarkup":false,
            "lastModifiedDateTime":"2011-06-02T19:30:28Z",
            "latest":true,
            "location":null,
            "mimeType":null,
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
   ]
}
```
Returns an error if the GUID is not valid.

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
