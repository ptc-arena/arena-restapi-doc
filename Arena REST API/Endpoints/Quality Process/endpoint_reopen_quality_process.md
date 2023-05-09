# POST Quality Process Reopen


/qualityprocesses/statuschanges

Completes a  object. 

NOTES:

* To execute this endpoint, the user must be the Quality Process owner or an Account Administrator.

* The user must be able to read and edit the Quality Process.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
```
{  
   "qualityProcess":{
       "guid":"K2M5O1MD03MI1K3MVZIC"
   },
   "complete":false,
   "comment":"CAR-000003 must be repopened."
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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Reopen a quality process



/qualityprocesses/statuschanges

```
{  
   "completedDateTime":null,
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
   "status":"OPEN",
   "statusMode":"AUTOMATIC",
   "targetCompletionDateTime":"2017-02-04T07:59:59Z",
   "template":{  
      "active":null,
      "guid":"2KN4N6J4VIL40J2L4N0B3"
   },
   "type":NULL
}
```
Returns an error if the Quality Process is already open.



```
{
  "status": 400,
  "errors": [
    {
      "code": 3089,
      "message": "The quality process is already open."
    }
  ]
}
```
