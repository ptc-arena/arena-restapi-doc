# PUT Quality Process Step Update (User Assignee)
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

Updates an existing Step object with a given GUID  in a Quality Process with a given GUID. 

Editable attributes: Assignee, attribute values,  dueDateTime.

When you specify dueDateTime for a step, only the date portion of the dueDateTime string is honored. Time always appears as 23:59:59 local time.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Set Null

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| setnull  |   | Append the URL with setnull=true to set dueDateTime to null. Attribute must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.  |

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

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
