# POST Item Specs Thumbnail Image Create From Files View
POST /items/&lt;GUID&gt;/image

This endpoint uploads an image to the Specs view thumbnail from the Files view of the same Item.

The guid must be an image file on the Files view of the  Item.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body 


```
{  
   "guid":"YG0J2F0REH0GZI8FYY2C"
}
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
If the File from the FIles view is successfully uploaded as the Specs Image this is the response:

```
{
   "guid":"YG0J2F0REH0GZI8FYY2C"
}
```
Returns an error  if the guid of the File is not associated with the Item..

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
