# GET Item Revisions
GET /items/&lt;GUID&gt;/revisions

Returns all Item Revision objects for an item with a given GUID. The revision type is specified by the value of the "status" attribute. 0 is working revision, 1 is effective revision, 2 is past revisions.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
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

## Sample Responses
Get all  revisions for an item

GET /items/Q8SBU2BB8P8P8MTGTTHH/revisions

```
{  
   "count":4,
   "results":[  
      {  
         "change":{  
            "creationDateTime":"2011-02-16T01:15:39Z",
            "deviated":false,
            "guid":null
         },
         "guid":"ASCVEMVVS9S9S6D0DDX3",
         "lifecyclePhase":{  
            "guid":"ASCVEMVVS9RUDWFYHWC3",
            "name":"In Production"
         },
         "notes":null,
         "number":null,
         "status":0,
         "supersededDateTime":null,
         "url": {
             "api": "https://api.arenasolutions.com/v1/items/ASCVEMVVS9S9S6D0DDX3",
             "app": "https://app.bom.com/ASCVEMVVS9S9S6D0DDX3"
      },
      {  
         "change":{  
            "creationDateTime":"2011-02-16T00:12:28Z",
            "deviated":false,
            "effectiveDateTime":"2011-02-16T01:15:39Z",
            "guid":null,
            "number":"ECO-000006"
         },
         "guid":"Q8SBU2BB8P8P8MTGTTHH",
         "lifecyclePhase":{  
            "guid":"ASCVEMVVS9RUDWFYHWC3",
            "name":"In Production"
         },
         "notes":null,
         "number":"B",
         "status":1,
         "supersededDateTime":null,
         "url": {
             "api": "https://api.arenasolutions.com/v1/items/Q8SBU2BB8P8P8MTGTTHH",
             "app": "https://app.bom.com/Q8SBU2BB8P8P8MTGTTHH"
      },
      {  
         "change":{  
            "creationDateTime":"2011-02-14T23:13:50Z",
            "deviated":false,
            "effectiveDateTime":"2011-02-16T00:12:28Z",
            "guid":null,
            "number":"ECO-000003"
         },
         "guid":"5N7Q9HQQN4N4N18V8836",
         "lifecyclePhase":{  
            "guid":"ASCVEMVVS9RUDWFYHWC3",
            "name":"In Production"
         },
         "notes":null,
         "number":"A",
         "status":2,
         "supersededDateTime":"2011-02-16T01:15:39Z",
         "url": {
             "api": "https://api.arenasolutions.com/v1/items/5N7Q9HQQN4N4N18V8836",
             "app": "https://app.bom.com/5N7Q9HQQN4N4N18V8836"
      },
      {  
         "change":{  
            "creationDateTime":"2011-02-11T16:52:39Z",
            "deviated":false,
            "effectiveDateTime":"2011-02-14T23:13:50Z",
            "guid":null
         },
         "guid":"BTDWFNWWTATAT7E1EHR7",
         "lifecyclePhase":{  
            "guid":"ASCVEMVVS9RUDWFYHWC3",
            "name":"In Production"
         },
         "notes":null,
         "number":"1",
         "status":2,
         "supersededDateTime":"2011-02-16T00:12:28Z",
         "url": {
             "api": "https://api.arenasolutions.com/v1/items/BTDWFNWWTATAT7E1EHR7",
             "app": "https://app.bom.com/BTDWFNWWTATAT7E1EHR7"
      }
   ]
}
```
Produces an error if the GUID is not valid.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
