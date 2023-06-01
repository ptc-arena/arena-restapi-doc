# GET File Corrections
/files/&lt;GUID&gt;/corrections

Returns a collection of corrected  File objects for a File with a given GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
```
{  
   "count": 5,
   "results":[  
      {  
         "correctedDateTime": "2020-09-16-T14:26:45Z",
         "correctedUser": {
            "guid": "608R5268J0JZI1RPMHYM",  
            "fullName":"Helen Rodgers"
            "email": "hrdogers@everyroadgps.com"
         },
         "file":{
            "author":{  
               "fullName":"Heidi Walker"
            },
            "category":{  
               "guid":"M4O7QY5R7FY8RATAYXNX"
            },
            "corrected": true,
            "creationDateTime":"2016-02-01T22:28:10Z",
            "description":"Assembly instructions",
            "edition":"3",
            "format":"pdf",
            "guid":"9ASCVEMTFV3M2L4NWYCGO",
           "hasMarkup":false,
           "lastModifiedDateTime":"2020-09-16-T14:26:45Z",
           "latest":true,
           "location":null,
           "locked":true,
           "mimeType":"text/plain",
           "name":"everyroad-500-schematic.pdf",
           "number":"FILE-000593",
           "private":false,
           "size":14081,
           "storageMethodName":"FILE",
           "title":"500 board schematic"
         },
         "guid": "9RBU859BM3K3M507915S",
         "notes": "Original File upload was incorrect. These are the correct documents."
      },
      ...
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
