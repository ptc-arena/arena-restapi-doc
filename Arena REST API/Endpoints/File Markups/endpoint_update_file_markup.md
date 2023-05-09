# PUT File Markup Update


/files/&lt;GUID&gt;/markups/&lt;GUID&gt;

Updates a   object.

Also supports updating File storageMethodName from FILE, FTP, WEB, or PLACE_HOLDER to FTP, WEB, or PLACE_HOLDER. This update can only be performed on unlocked Files.

Updating storageMethodName to  FTP, WEB, or PLACE_HOLDER also requires including the attribute location.

This endpoint does not support updating the storageMethodName from FTP, WEB, or PLACE_HOLDER to FILE. This requires a POST call. See POST File  Update.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set markup.format to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

## Sample Request Body


This example shows all editable attributes.

```
markup.storageMethodName: FILE
markup.content: <file stream>
markup.category.guid: Q8SBPMQS3K3J2LC0SX84
markup.title: SmartWall 3000 Updated Drawing
markup.format: PDF
markup.author.fullName: John Sneath
reserved: false
```
## Sample Request Body - Updating storageMethodName
In this example, the existing File  has a storageMethodName of FILE and through the PUT endpoint we're updating it to storageMethodName of WEB.

```
{
    "markup": {
        "storageMethodName": "WEB",
        "location":"www.everyroadgps.com/en_US/2021-update-file.html",
        "title":"Proposed 2021 Update",
        "format":"pdf",
        "author": {
            "fullName":"Rachel Borger"
        }
    },
    "reserved": false
}
```
## Sample Request Body - Set markup.format to Null
In this example. the markup.format is set to null.

PUT /files/&lt;GUID&gt;/markups/&lt;GUID&gt;?setnull=true

```
markup.storageMethodName: FILE
markup.content: <file stream>
markup.category.guid: Q8SBPMQS3K3J2LC0SX84
markup.title: SmartWall 3000 Updated Drawing
markup.format: null
markup.author.fullName: John Sneath
reserved: false
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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Responses
Update the details of a file



files/&lt;GUID&gt;/markups/&lt;GUID&gt;

```
{
    "guid": "ASCVERC3QT7WFYOVDX3P",
    "markup": {
        "author": {
            "fullName": "John Sneath"
        },
        "category": {
            "guid": "Q8SBPMQS3K3J2LC0SX84"
        },
        "creationDateTime": "2021-01-22T03:22:20Z",
        "format": "PDF",
        "guid": "EWGZIVG7UXGWFYOVDX3G",
        "lastModifiedDateTime": "2021-01-22T03:32:58Z",
        "locked": false,
        "storageMethodName": "FILE",
        "title": "SmartWall 3000 Updated Drawing"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": false
}
```
Updates the storageMethodName of a File from FILE to WEB.

```
{
    "guid": "ASCVERC3QT7WFYOVDX3P",
    "markup": {
        "author": {
            "fullName": "Rachel Borger"
        },
        "category": {
            "guid": "2K4N6J4VIL4EXGV223PR"
        },
        "creationDateTime": "2021-01-22T03:22:20Z",
        "format": "pdf",
        "guid": "EWGZIVG7UXGWFYOVDX3G",
        "lastModifiedDateTime": "2021-01-22T03:32:58Z",
        "location":"www.everyroadgps.com/en_US/2021-update-file.html",
        "locked": false,
        "storageMethodName": "WEB",
        "title": "Proposed 2021 Update"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": false
}
```
Updates the file markup to null.

PUT /files/&lt;GUID&gt;/markups/&lt;GUID&gt;?setnull=true

```
{
    "guid": "ASCVERC3QT7WFYOVDX3P",
    "markup": {
        "author": {
            "fullName": "John Sneath"
        },
        "category": {
            "guid": "Q8SBPMQS3K3J2LC0SX84"
        },
        "creationDateTime": "2021-01-22T03:22:20Z",
        "format": null,
        "guid": "EWGZIVG7UXGWFYOVDX3G",
        "lastModifiedDateTime": "2021-01-22T03:32:58Z",
        "locked": false,
        "storageMethodName": "FILE",
        "title": "SmartWall 3000 Updated Drawing"
    },
    "markupOf": {
        "edition": "1",
        "guid": "UCWFYBWNADWCVEGZ24RC",
        "number": "FILE-000944"
    },
    "reserved": false
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"EWGZDAEGR8R1K3J1LPP3\" is not valid."
      }
   ]
}
```
