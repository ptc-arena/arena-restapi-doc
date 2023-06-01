# GET Quality Process Number Formats
/settings/qualityprocesses/numberformats

/settings/qualityprocesses/numberformats/&lt;GUID&gt;

This returns  Quality Process Number Formats available in the workspace. Appending a GUID to the URL returns the number format with that GUID.  

Quality Process Number Formats consist of a list of  prefixes and an auto-incrementing number field.

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
| Content-Length<br> | number<br> | number of characters in the response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all Quality Process number formats defined for the workspace

/settings/qualityprocesses/numberformats

```
{  
   "count":3,
   "results":[  
      {  
         "creationDateTime":"2015-12-14T19:40:54Z",
         "guid":"YG0J2A8OX0JSBUDWFUYM",
         "lastUsed":"000000",
         "name":"8D",
         "nextValue":"000001",
         "prefixes":[  
            {  
               "guid":"SAUDW42IRUCWFYH0JYZ4",
               "value":"8D-"
            }
         ]
      },
      {  
         "creationDateTime":"2015-12-14T19:40:54Z",
         "guid":"ZH1K3B9PY1KTCVEXGVZ3",
         "lastUsed":"000000",
         "name":"CAR",
         "nextValue":"000001",
         "prefixes":[  
            {  
               "guid":"5N7Q9HFV47P9SBUDWBK4",
               "value":"CAR-"
            }
         ]
      },
      {  
         "creationDateTime":"2015-12-14T19:40:54Z",
         "guid":"0I2L4CAQZ2LUDWFYHW0U",
         "lastUsed":"000000",
         "name":"NCMR",
         "nextValue":"000001",
         "prefixes":[  
            {  
               "value":"NCMR-",
               "guid":"6O8RAIGW58QATCVEXCLD"
            },
            {  
               "value":"NCMR2-",
               "guid":"7F7LWXOV17KWPAUDNCIT"
            }
         ]
      }
   ],
   "statusCode":0
}
```
Get a Quality Process number format with a specific GUID

/settings/qualityprocesses/numberformats/SAUDW42IRUCWFYH0JYZ4

```
{  
   "creationDateTime":"2015-12-14T19:40:54Z",
   "guid":"YG0J2A8OX0JSBUDWFUYM",
   "lastUsed":"000000",
   "name":"8D",
   "nextValue":"000001",
   "prefixes":[  
      {  
         "guid":"SAUDW42IRUCWFYH0JYZ4",
         "value":"8D-"
      }
   ]
}
```
