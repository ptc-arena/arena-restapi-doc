# GET Extracts Search
/extracts

Returns a collection of Extract objects \(but not the extract run content\) matching the given search criteria.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all extracts where results should begin. All extracts before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. By default the maximum number of extracts is 20. Can return up 400 extracts.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| name  | string  | Data Extract name  |
| creator.fullName  | string  | The integration user which is specified in the Setup view for the Extract in the account administration tool in Arena  |
| enabled  | true or false  | whether or not the Extract is enabled in the workspace  |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
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
