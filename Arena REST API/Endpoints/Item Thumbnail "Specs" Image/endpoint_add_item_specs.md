# POST Item Specs Thumbnail Image Create
POST /items/&lt;GUID&gt;/image

This endpoint uploads an image to the Item's  Specs view.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | multipart/form-data<br> |   |

## Sample Request Body
File attribute:

```
content: [physical file]
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
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
* When uploading a File as an Items Specs Image (also known as a Thumbnail Image):

* no JSON response if successful.

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
