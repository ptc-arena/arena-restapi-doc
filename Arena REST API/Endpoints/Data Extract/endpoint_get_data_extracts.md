# GET Extracts Search


/extracts

Returns a collection of  objects \(but not the extract run content\) matching the given search criteria.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all extracts where results should begin. All extracts before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of extracts is 20. Can return up 400 extracts.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | Data Extract name<br> |
| creator.fullName<br> | string<br> | The integration user which is specified in the Setup view for the Extract in the account administration tool in Arena<br> |
| enabled<br> | true or false<br> | whether or not the Extract is enabled in the workspace<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

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
Get all extracts \(note that only 1 extract can be defined per workspace\)

GET /extracts

```
{  
   "count":1,
   "results":[  
      {  
         "creationDateTime":"2015-03-19T15:33:43Z",
         "creator":{  
            "fullName":"Heidi Walker"
         },
         "enabled":true,
         "guid":"N5P8RZ6S8GZRATCVEXEL",
         "name":"October Change Cycle Time"
      }
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
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
