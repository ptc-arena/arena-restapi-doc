# POST Quality Process Complete


/qualityprocesses/statuschanges

Completes a  object. 

NOTES:

* To execute this endpoint, the user must be the Quality Process owner or an Account Administrator.

* The user must be able to read and edit the Quality Process.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "qualityProcess":{
       "guid":"K2M5O1MD03MI1K3MVZIC"
   },
   "complete":true,
   "comment":"CAR-000003 has been resolved."
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
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Complete a quality process



/qualityprocesses/statuschanges

```
{  
   "completedDateTime":"2019-07-05T21:57:22Z",
   "creationDateTime":"2017-01-20T19:35:37Z",
   "creator":{  
      "fullName":"Heidi W",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "currentStep":{  
      "approvals":null,
      "attributes":null,
      "guid":"Q6Q9S5QH47QMFO7QZ3MG"
   },
   "description":"Products have been melting at high temps.",
   "guid":"K2M5O1MD03ML1K3MVZIC",
   "name":"Everyroad bezels melted/burned.",
   "number":"CAR-000003",
   "owner":{  
      "fullName":"Heidi W",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "status":"COMPLETED",
   "statusMode":"AUTOMATIC",
   "targetCompletionDateTime":"2017-02-04T07:59:59Z",
   "template":{  
      "active":null,
      "guid":"2KN4N6J4VIL40J2L4N0B3"
   },
   "type":NULL
}
```
Returns an error if the Quality Process is already completed.



```
{
  "status": 400,
  "errors": [
    {
      "code": 3089,
      "message": "The quality process is already completed."
    }
  ]
}
```
