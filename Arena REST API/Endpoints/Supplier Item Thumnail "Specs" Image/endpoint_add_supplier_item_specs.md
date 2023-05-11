# POST Supplier Item Specs Thumbnail Image Create


POST /supplieritems/&lt;GUID&gt;/image

This endpoint uploads an image to the Supplier Item's Specs view thumbnail.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | multipart/form\-data |   |

## Sample Request Body
File attribute:

```
content: [physical file]
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
No JSON response if successful.

An error message is returned if the file is not a valid image file. In the example below, the error message was encountered after attempting to upload an audio file as a thumbnail.

```
{
   "status":400,
   "errors": [
       {
           "code": 3094,
           "message": "The specified file is not a valid image."
       }
   ]
}
```
