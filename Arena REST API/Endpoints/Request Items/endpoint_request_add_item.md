# POST Request Item Add
/requests/&lt;GUID&gt;/items

Adds an item to a request with a specific GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
