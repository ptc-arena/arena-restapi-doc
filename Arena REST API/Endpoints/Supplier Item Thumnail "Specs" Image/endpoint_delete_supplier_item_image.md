# DELETE Supplier Item Thumbnail Image
DELETE /supplieritems/&lt;GUID&gt;/image

Deletes the Supplier Item Image Thumbnail Image of an Supplier Item with a specific GUID. The Supplier Item Thumbnail Image is located in the Specs view of a Supplier Item.   

## Request Headers

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 204  | Success  |
| 400  | Failure  |

## Response Headers

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Successful Response Body
no response

## Unsuccessful Response Body

| Name  | Description  |
|  --- |  --- | 
| status  | HTTP status  |
| errors  | Collection of errors, including an Arena error code and message for each.  |

## Sample Responses
No JSON response if successful.

Failure - 400

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
