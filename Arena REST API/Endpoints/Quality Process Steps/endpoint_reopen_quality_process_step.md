# POST Quality Process Step Reopen
/qualityprocesses/statuschanges

Reopens a Quality Process step. 

NOTES:
          
          
          
          
          
        

* Assigned Quality Process steps (excluding sign-off steps) can be reopened by the Quality Process Step Assignee or the Quality Process Owner.

* Quality Process steps without an assignee (excluding sign-off steps) can be reopened by any user with permissions.

* Quality Process steps (exluding sign-off steps) cannot be reopened if the Quality Process itself is completed.

* Quality Process approved sign-off steps cannot be reopened or reversed by this endpoint.

* For Access Policies: A user must have the Quality Edit Details rule enabled to reopen a Quality Process step.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "qualityProcess":{
       "guid":"K2M5O1MD03MI1K3MVZIC",
       "step": {
           "guid": "8QAT748L1KFYH0JOGNB"
       { 
   },
   "complete": false,
   "comment": "Correcting typos within the Problem Description field."
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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Reopens a quality process step

/qualityprocesses/statuschanges

```
{
   "qualityProcess":{  
       "completedDateTime":"2019-07-25T13:51:25Z",
       "creationDateTime":"2017-01-20T19:35:37Z",
       "creator":{  
           "email": "hwalker@everyroadgps.com",
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
           "email": "hwalker@everyroadgps.com", 
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
   "complete": false,
   "comment": "Correcting typos within the Problem Description field."
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
