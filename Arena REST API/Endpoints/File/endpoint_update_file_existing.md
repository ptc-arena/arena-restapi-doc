# POST File Update


/files/&lt;GUID&gt;

Updates an existing File with storageMethodName FTP, WEB, or PLACE_HOLDER to FILE .

To update an existing File with a storageMethodName of FILE to FTP, WEB, or PLACE_HOLDER please refer to the PUT File Summary Update endpoint.

Construct a request with  content\-type "multipart/form\-data" \(in the header of the request\) and file content.

Currently, only Files less than 2GB can be uploaded through this endpoint.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |

## Sample Request Body
Starting with an existing File with a storageMethodName of FTP, WEB, or PLACE_HOLDER:

```
author.fullName: George Lewis
category.guid: 7P9S6379K1KUDWCUEIJG
description: Schematic Drawing
edition: 1
format: pdf
private: false
storageMethodName: FILE
title: Drawing for Model 3000
content: <file stream>
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | determined by file type<br> | content type of file<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-File\-GUID<br> | GUID string<br> | GUID for new file \- only when including content.<br> |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
