# POST File Correct
/files/&lt;guid&gt;/corrections

Creates a corrected File object.

To correct a File, the Corrections to Files Allowed setting must be set to Yes, and allow removal of original content or Yes, but don't allow removal of original content. File corrections will not be supported if the Corrections to Files Allowed setting is set to No.

The removeOriginalContent attribute can only be set to true if the Corrections to Files Allowed setting is set to Yes, and allow removal of original content. 

Only locked Files can be corrected.

Only Files that are not checked out can be corrected.

User needs a full license to correct a File.

Access Policy users require an edit File summary rule to correct a File.

Currently, only Files less than 2GB can be uploaded through this endpoint.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | multipart/form-data<br> |   |

## Sample Request Body - with uploaded content
Text attributes:

```
comments: "Previous upload contained an incorrect drawing. Uploading the correct File in this call.",
storageMethodName: "FILE",
removeOriginalContent: true,
```
File attribute:

```
content: [physical file]
```
## Sample Request Body - no uploaded content


```
{  
   "comments": "Correcting typo in File Title.",
   "storageMethodName":"WEB",
   "removeOriginalContent": false,
   "location": "https://www.everyroadgps.com/products/9828395"
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | determined by file type<br> | content type of file<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-File-Guid<br> | GUID string<br> | GUID for correct file - only when including content<br> |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
* When correcting a File object with uploaded content:

* no JSON response. Please refer to the response header for file information.

* When correcting a file with no uploaded content:

```
{  
   "correctedDateTime": "2020-09-12-T12:00:05Z",
   "correctedUser": {
      "email": "hrdogers@everyroadgps.com",
      "fullName":"Helen Rodgers",
      "guid": "938R5268J0JZI1RPMHYM"  
   },
   "file":{
      "author":{  
         "fullName":"John Parker"
      },
      "category":{  
         "guid":"ZH0J2L4EXGS0NF91"
      },
      "corrected": true,   
      "creationDateTime":"2014-02-24T22:41:19Z",
      "description":"500 board early spec",
      "edition":"2",
      "format":"PDF",
      "guid":"GYI16WW251K0J2TITQ1O",
      "hasMarkup":false,
      "lastModifiedDateTime":"2020-09-12-T12:00:05Z",
      "latest":true,
      "location":"www.everyroadgps.com/files",
      "locked":false,
      "mimeType":null,
      "name":null,
      "number":"FILE-000005",
      "private":false,
      "size":null,
      "storageMethodName":"WEB",
      "title":"some title",
   },   
   "guid": "4ZYU859BM3K3M507915S",
   "notes": null
}

```
Returns an error  if  File Correction is a JSON request and the location  attribute is missing.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3001,
         "message":"The attribute \"location\" is required."
      }
   ]
}
```
Returns an error if File size is 2GB or higher.

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
