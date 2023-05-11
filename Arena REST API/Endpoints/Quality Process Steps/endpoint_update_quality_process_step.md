# PUT Quality Process Step Update (Deprecated)


/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

Updates an existing  object with a given GUID  in a Quality Process with a given GUID. 

Editable attributes: Assignee, attribute values,  dueDateTime.

When you specify dueDateTime for a step, only the date portion of the dueDateTime string is honored. Time always appears as 23:59:59 local time.

Please note that the  response object is deprecated. Please use  when assigning a user or User Group to a Quality Proecss step. See note attached to  object body within response body.

## Request Header
## Sample Request Body
```
{  
   "dueDateTime":"2016-11-20T00:00:00Z",
   "assignee":{  
      "guid":"2K4N6EL7NVCVEXGZI8QJ"
   },
   "attributes":[  
      {  
         "guid":"6O8RAIPBRZIEXGZI1HZ1",
         "value":"Send notification email"
      }
   ]
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
Update a quality process step



/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

```
{  
   "approvals":null,
   "assignee":{
       "deprecated": true,
       "fullName":"John Parker",
       "guid":"7P9SBJSSP6N6P8RATPM6",
       "note": "The assignee response object is deprecated. Please use assignees."
   },
   "assignees": {
       "users": [
           {
               "fullName": "John Parker",
               "guid": "7P9SBJSSP6N6P8RATPM6"
           }
       ]
   },
   "attributes":[  
      {  
         "guid":"1J3M5DK6MUD9SBUDWCUV",
         "name":"Serial Number(s) of Nonconforming Parts"
      },
      {  
         "guid":"2K4N6EL7NVEATCVEXDVS",
         "name":"Inventory Impact?",
         "value":"N/A"
      },
      {  
         "guid":"3L5O7FM8OWFBUDWFYEWF",
         "name":"Inventory Impact description"
      },
      {  
         "guid":"4M6P8GN9PXGCVEXGZFXC",
         "name":"Supplier Containment actions required"
      },
      {  
         "guid":"5N7Q9HOAQYHDWFYH0GYB",
         "name":"Internal Containment actions required"
      },
      {  
         "guid":"6O8RAIPBRZIEXGZI1HZ1",
         "name":"Customer Containment actions required",
         "value":"Send notification email"
      }
   ],
   "completeDateTime":null,
   "completeUser":null,
   "dueDateTime":"2016-11-20T07:59:59Z",
   "guid":"DVFYHPWIY6PL4N6P82C8",
   "name":"Immediate Containment",
   "order":3,
   "status":"OPEN",
   "type":"REGULAR"
}
```
Returns an error if the GUID is not valid:

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"CUB5FVEN6P8RAQI\" is not valid."
    }
  ]
}
```
