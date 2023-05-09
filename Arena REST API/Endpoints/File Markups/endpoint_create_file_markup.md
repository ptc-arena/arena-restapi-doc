# POST File Markup Create


/files/&lt;GUID&gt;/markups

Creates a File Markup  object.

If you wish to create a File record and upload file content to the Arena servers, construct a request that is content type multipart/form\-data \(specified in the header\) and has a storageMethodName of FILE \(stored on Arena servers.\)

If you wish to create a File record with no uploaded content, construct a JSON request with a storageMethodName of FTP \(stored on user FTP server\), WEB \(web link\), or PLACE_HOLDER \(will upload content later\). 

When the storageMethod is FTP or WEB, the location attribute should be the web or ftp address where the file resides.
For Files with storageMethodName FILE, the location attribute is not used.

Currently, only Files less than 2GB can be uploaded through this endpoint.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | multipart/form\-data |   |

## Sample Request Body - with uploaded content
Text attributes:

```
reserved:true
markup.author.fullName:James Yan
markup.format:pdf
markup.title:Checkin Endpoint Test Update
markup.storageMethodName:FILE
markup.category.guid:0I2L4H2TGJ2CVET001OY
```
File attribute:

```
content: [physical file]
```
## Sample Request Body - no uploaded content


```
{
    "markup": {
        "storageMethodName": "WEB",
        "location":"www.arenasolutions.com/winter_tour_2021.com",
        "title":"Winter 2021 Tour",
        "format":"pdf",
        "author": {
            "fullName":"James Deckard"
        }
    },
    "reserved": true
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | determined by file type | content type of file |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-FileGuid | GUID string | GUID for new file \- only when including content |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Responses
* When creating a File object with uploaded content:

```
{
    "guid": "M4O7Q3OF25J8RA07P9FJ",
    "markup": {
        "author": {
            "fullName": "James Yan"
        },
        "category": {
            "guid": "0I2L4H2TGJ2CVET001OY"
        },
        "creationDateTime": "2021-01-22T19:51:01Z",
        "format": "pdf",
        "guid": "Q8SBU7SJ69S8RA07P9F9",
        "lastModifiedDateTime": "2021-01-22T19:51:01Z",
        "locked": false,
        "mimeType": "application/pdf",
        "name": "Checkin Endpoint Test.pdf",
        "size": 15148,
        "storageMethodName": "FILE",
        "title": "Checkin Endpoint Test Update"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": true,
    "reservedUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
* When creating a file with no uploaded content:

```
{
    "guid": "ASCVERC3QT7WFYOVDX3P",
    "markup": {
        "author": {
            "fullName": "James Desckard"
        },
        "category": {
            "guid": "2K4N6J4VIL4EXGV223PR"
        },
        "creationDateTime": "2021-01-22T03:22:20Z",
        "format": "pdf",
        "guid": "EWGZIVG7UXGWFYOVDX3G",
        "lastModifiedDateTime": "2021-01-22T03:22:20Z",
        "location": "www.ftp.com",
        "locked": false,
        "storageMethodName": "WEB",
        "title": "Winter 2021 Tour"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": true,
    "reservedUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
Returns an error  if a required metadata attribute is missing.

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
