# POST Supplier Item File Create
/supplieritems/&lt;GUID&gt;/files/

Creates a new File Association object and associates it with a supplier item with a given GUID.

If you wish to create a File record with no uploaded content, construct a JSON request with a storageMethodName of PLACE_HOLDER, FTP, or WEB. When the storageMethodName is FTP or WEB, the location attribute should be the web or ftp address where the file resides.


If you wish to create a File record and upload file content to the Arena servers, construct a request that is content type multipart/form-data and has a storageMethodName  of FILE. 


For File editions with storageMethodName FILE, the location attribute should be null.

Currently, only Files less than 2GB can be uploaded through this endpoint.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | multipart/form-data<br> |   |

## Sample Request Body

          
          
        

* Creating a File and uploading content to Arena servers (example form):

```
author.fullName:John Parker
category.guid:ZH0J2L4EXGS0NF91
description:Assembly Instructions
edition:B-1
format:pdf
name:Assy Instructions
private:false
storageMethodName:FILE
title:Assembly Instructions for 424-0263
comment:New edition with updated file
content:[physical file]
```
* Creating a File with no uploaded content:

```
{
    "file": {
      "author": { 
         "fullName": "Jamie Moore"
      },
      "category": { 
         "guid": "TBVEJ9AAJQ9J2LX5TMTB" 
      },
      "description": "Trilby Tech website",
      "edition": "1",
      "location": "http://www.trilbytech.com",
      "mimeType": null,
      "name": "Trilby site",
      "private":false,
      "storageMethodName": "WEB",
      "title": "Trilby Web Site"
    },
    "primary":true
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
| X-Arena-ItemFileAssociation-Guid<br> | GUID string<br> | GUID for new file association - only when including content<br> |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
* When creating a File object with uploaded content:

* No JSON Response. Please refer to the response header for file information.

* When creating a file with no uploaded content:

```
{
    "file": {
      "author": {
      "fullName": "Jamie Moore"
    },
    "category": {
      "guid": "TBVEJ9AAJQ9J2LX5TMTB"
    },
    "creationDateTime": "2017-01-30T21:29:03Z",
    "description": "Trilby Tech website",
    "edition": "1",
    "format": null,
    "guid": "2K4NSIJJSZIYH0Q4AKZN",
    "hasMarkup":false,
    "lastModifiedDate": null,
    "lastModifiedDateTime": "2017-01-30T21:29:03Z",
    "latest":true,
    "location": "http://www.trilbytech.com",
    "locked":false,
    "mimeType": null,
    "name": "Trilby site",
    "number": "FILE-000998",
    "private":false,
    "size": 0,
    "storageMethod": 3,
    "storageMethodName": "WEB",
    "title": "Trilby Web Site"
      },
    "guid": "UCWFKABBKR9DWFB70NXB",
    "primary":true
}

```
An error is returned if:
          
          
          
        

* The GUID is not valid.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
* a required metadata attribute is missing.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3001,
      "message": "The attribute \"file.edition\" is required."
    }
  ]
}
```
* Returns an error if File size is 2GB or higher.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3033,
      "message": "The file content is missing."
    }
  ]
}
```
