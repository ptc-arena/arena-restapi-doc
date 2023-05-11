# GET Supplier Item File Association


/supplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns a  object with a given GUID belonging to a supplier item with a given GUID. 

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
Get a single file association from a given supplier item



/supplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;

```
{  
   "file":{  
      "author":{  
         "fullName":"John Parker"
      },
      "category":{  
         "guid":"Z9TCH788TO7H0JV3RPLF",
         "name":"Design Drawing",
         "path":"File\\Engineering\\Product Requirements Doc" 
      },
      "checkedOut": false,       
      "corrected": false,
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
