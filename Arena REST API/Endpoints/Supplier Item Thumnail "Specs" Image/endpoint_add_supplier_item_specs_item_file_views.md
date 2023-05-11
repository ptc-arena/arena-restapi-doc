# POST Supplier Item Specs Thumbnail Image Create From Files View


POST /supplieritems/&lt;GUID&gt;/image

This endpoint uploads an image to the Specs view thumbnail.

The guid must be an image file on the Files view of the Supplier Item.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body


```
{  
   "guid":"5N7Q9M7YLO7N6PSJ5BSL"
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
| X\-Arena\-FileGuid<br> | GUID string<br> | GUID for new file \- only when including content<br> |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
