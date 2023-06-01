# PUT Quality Process Step Update (User Assignee)
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

Updates an existing Step object with a given GUID  in a Quality Process with a given GUID. 

Editable attributes: Assignee, attribute values,  dueDateTime.
          
        

When you specify dueDateTime for a step, only the date portion of the dueDateTime string is honored. Time always appears as 23:59:59 local time.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set dueDateTime to null. Attribute must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

## Sample Request Body
PUT /qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

```
{
    "assignees": {
        "users": [
            {
                "guid": "2K4N6EL7NVCVEXGZI8QJ"
            }
        ]
    },
    "attributes": [
        {
            "guid": "6O8RAIPBRZIEXGZI1HZ1",
            "value": "Send notification email"
        }
    ],
    "dueDateTime": "2021-08-08T15:00:00Z"
}
```
PUT /qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;?setnull=true

```
{
    "assignees": {
        "users": [
            {
                "guid": "2K4N6EL7NVCVEXGZI8QJ"
            }
        ]
    },
    "attributes": [
        {
            "guid": "6O8RAIPBRZIEXGZI1HZ1",
            "value": "Send notification email"
        }
    ],
    "dueDateTime": null
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
Update a quality process step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

```
{  
   "approvals":null,
   "assignee":{
     "deprecated": true,
     "fullName":"REST API Admin",
     "guid":"2K4N6EL7NVCVEXGZI8QJ",
     "note": "The assignee response object is deprecated. Please use assignees."
   },
   "assignees":{
     "users":[
       {  
          "fullName":"REST API Admin",
          "guid":"2K4N6EL7NVCVEXGZI8QJ"
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
   "dueDateTime":"2021-08-08T15:00:00Z",
   "guid":"DVFYHPWIY6PL4N6P82C8",
   "name":"Immediate Containment",
   "order":3,
   "status":"OPEN",
   "type":"REGULAR"
}
```
Updates dueDateTime to null.

PUT /qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;?setnull=true

```
{  
   "approvals":null,
   "assignee":{
     "deprecated": true,
     "fullName":"REST API Admin",
     "guid":"2K4N6EL7NVCVEXGZI8QJ",
     "note": "The assignee response object is deprecated. Please use assignees."
   },
   "assignees":{
     "users":[
       {  
          "fullName":"REST API Admin",
          "guid":"2K4N6EL7NVCVEXGZI8QJ"
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
   "dueDateTime":null,
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
