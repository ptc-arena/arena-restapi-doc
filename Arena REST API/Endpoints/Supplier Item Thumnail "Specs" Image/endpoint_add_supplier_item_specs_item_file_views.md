# POST Supplier Item Specs Thumbnail Image Create From Files View


POST /supplieritems/&lt;GUID&gt;/image

This endpoint uploads an image to the Specs view thumbnail.

The guid must be an image file on the Files view of the Supplier Item.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body


```
{  
   "guid":"5N7Q9M7YLO7N6PSJ5BSL"
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
When creating a file with no uploaded content:

```
{  
   "guid":"5N7Q9M7YLO7N6PSJ5BSL"
}
```
Returns an error  if the file is not a valid image file..

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3094,
         "message":"The file must be associated with the item (supplier item)."
      }
   ]
}
```
