# POST Item Specs Thumbnail Image Create From Files View


POST /items/&lt;GUID&gt;/image

This endpoint uploads an image to the Specs view thumbnail from the Files view of the same Item.

The guid must be an image file on the Files view of the  Item.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body 


```
{  
   "guid":"YG0J2F0REH0GZI8FYY2C"
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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | determined by file type<br> | content type of file<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
