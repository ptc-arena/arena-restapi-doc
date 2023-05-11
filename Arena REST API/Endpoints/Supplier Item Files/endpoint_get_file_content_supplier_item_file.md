# GET Supplier Item File Content


/suppplieritems/&lt;GUID&gt;/files/&lt;GUID&gt;/content

Returns file content belonging to a file with a given GUID, which is associated with a supplier item with a given GUID. 

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
| Content\-Type | determined by file type | content type of file |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Responses
Returns the content of the File as an InputStream.

An error is returned if:

* the GUID is not valid.

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
* An error is thrown by the file server

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3017,
         "message":"The file with guid \"7P60AQ9P8RAS7F6J\" cannot be downloaded at this time."
      }
   ]
}
```
* \*If the file server is inaccessible, it may return a 400 status with no message.

