# POST File Content Update
/files/&lt;GUID&gt;/content

Updates the content of a File edition, replacing the previous content.

Construct a request with  content-type "multipart/form-data" \(in the header of the request\) and file content.

Currently, only Files less than 2GB can be uploaded through this endpoint.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |

## Sample Request Body
File attribute:

```
content: [physical file]
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
| Content-Type  | determined by file type  | content type of file  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Responses
no JSON response

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
* A required metadata attribute is missing.

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
* Returns an error if File size is 2GB or higher.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3033,
         "message":"The file content is missing."
      }
   ]
}
```
