# POST File Check Out
/files/checkoutstatuschanges

Checks out a File Edition. Note that only the latest edition can be checked out and only files of storageMethod "FILE" can be checked out.

Checking Out a File occurs with the expectation to make changes to the File. File Check Out is more of a workflow than the editing of an existing File resoruce. Due to this workflow nature, existing File endpoints cannot be used and a POST with a files/statuschanges endpoint is utilized.
The File Edition guid is submitted within the request body.

Users must have a Full license to perform a File Check Out. Access Policies users must have access to an Edit File Policy rule.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body


```
{  
  "checkedOut": true,
  "comment": "Checking Out For Review",
  " file": { 
       "guid": "K2M501MD03M2L47YKQ5B"
  }
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
| X-Arena-FileGuid<br> | GUID string<br> | GUID for new file - only when including content<br> |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
* Checking Out a File that has not been Checked Out:

```
{  
   "checkedOut": true,
   "comment": "Checking Out File for Review",
   "file": {
       "author": {
           "fullName": "Heidi Walker"
       },
       "category": {
           "guid": "3L507K5WJM5FYHW334R7"
       ",
       "checkedOut": true,
       "checkoutDateTime": "2020-10-30T19:20:11Z",
       "checkoutUser": {
           "email": "hwalker@everyroadgps.com",
           "fullName": "Heidi Walker",
           "guid": "DVFYHUF6TWDWFYH01WZB"
       },
       "corrected": false,
       "creationDateTime": "2018-06-02T19:30:28Z",
       "description": null,
       "edition": "2",
       "format": "pdf",
       "guid": "K2M501MD03M2L47YKQ5B",
       "hasMarkup": false,
       "lastModifiedDateTime": "2019-06-02T19:30:28Z",
       "latest": true,
       "location": null
       "locked": true,
       "mimeType": application/pdf
       "name": USB Cable A-A Datasheet.pdf",
       "number": "FILE-000867",
       "private": false,
       "size": 12326,
       "storageMethod": 0,
       "storageMethodName": "FILE",
       "title": "USB CABLE A-A Datasheet"
          
}
```
An error is returned if a user attempts to Check Out a File that is already Checked Out.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3133,
         "message":"The File cannot be updated."
      }
   ]
}
```
