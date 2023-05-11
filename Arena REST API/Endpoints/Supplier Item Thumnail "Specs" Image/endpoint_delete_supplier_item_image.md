# DELETE Supplier Item Thumbnail Image


DELETE /supplieritems/&lt;GUID&gt;/image

Deletes the Supplier Item Image Thumbnail Image of an Supplier Item with a specific GUID. The Supplier Item Thumbnail Image is located in the Specs view of a Supplier Item.   

## Request Headers

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 204<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Headers

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Successful Response Body
no response

## Unsuccessful Response Body

| Name<br> | Description<br> |
|  --- |  --- | 
| status<br> | HTTP status<br> |
| errors<br> | Collection of errors, including an Arena error code and message for each.<br> |

## Sample Responses
No JSON response if successful.

Failure \- 400

An error is returned if:

* The GUID is not valid. 

```
{  
   "status":403,
   "errors":[  
      {  
         "code":3024,
         "message":"Either you do not have privileges to access the requested data or it does not exist."
      }
   ]
}
```
