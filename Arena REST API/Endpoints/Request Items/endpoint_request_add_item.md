# POST Request Item Add


/requests/&lt;GUID&gt;/items

Adds an item to a request with a specific GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
Add an item to a request, specifying notes.



/requests/&lt;GUID&gt;/items

```
{
  "item": {
    "guid": "1J3M5I3UHK3BUCLB5AED"
  },
  "notes": "This is overheating the forward unit."
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
```
{
    "guid": "DVFYHUF6TW98RAB185YV",
    "item": {
        "guid": "1J3M5I3UHK3BUCLB5AED",
        "name": "Manual, Everyroad Model 300/500",
        "number": "770-00001",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/3L5O7K5WJM5DWEO7JBIR",
            "app": "https://app.bom.com/3L5O7K5WJM5DWEO7JBIR"
        }
    },
    "notes": "This is overheating the forward unit."
}
```
Request with invalid GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
