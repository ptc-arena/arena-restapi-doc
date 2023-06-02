# PUT Quality Process Update
/qualityprocesses/&lt;GUID&gt;

Updates the metadata of a Quality Process object with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Set Null

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| setnull  |   | Append the URL with setnull=true to set description, targetCompletionDate, or type to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.  |

## Sample Request Body
PUT /qualityprocesses/&lt;GUID&gt;

```
{  
   "description":"Quality Process with updated name",
   "name":"New Process Introduction",
   "type":"Manufacturing"
}
```
PUT /qualityprocesses/&lt;GUID&gt;?setnull=true

```
{  
   "description":"Quality Process with updated name",
   "name":"New Process Introduction",
   "type":null
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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

## Sample Response Body
Update the details of a quality process

/qualityprocesses/&lt;GUID&gt;

```
{  
   "completedDateTime":null,
   "creationDateTime":"2016-04-26T16:48:47Z",
   "creator":{  
      "fullName":"Roy S",
      "guid":"7P9SXNOOX4L4N6P8BG6R"
   },
   "currentStep":{  
      "approvals":null,
      "attributes":null,
      "guid":"R9TCH788HO73M5O7N980"
   },
   "description":"Quality Process with updated name",
   "guid":"Q8SBG677GN62L4N6M876",
   "name":"New Process Introduction",
   "number":"8D-000010",
   "owner":{  
      "fullName":"Heidi Walker",
      "guid":"I0K38YZZ8FWFYH0JSIPF"
   },
   "status":"OPEN",
   "statusMode":"AUTOMATIC",
   "targetCompletionDateTime":null,
   "template":{  
      "active":null,
      "guid":"6O8RWMNNW3MI1K3M2TOK"
   },
   "type":"Manufacturing"
}
```
Set Quality Process Step attribute to null.

PUT /qualityprocesses/&lt;GUID&gt;?setnull=true

```
{  
   "completedDateTime":null,
   "creationDateTime":"2016-04-26T16:48:47Z",
   "creator":{  
      "fullName":"Roy S",
      "guid":"7P9SXNOOX4L4N6P8BG6R"
   },
   "currentStep":{  
      "approvals":null,
      "attributes":null,
      "guid":"R9TCH788HO73M5O7N980"
   },
   "description":"Quality Process with updated name",
   "guid":"Q8SBG677GN62L4N6M876",
   "name":"New Process Introduction",
   "number":"8D-000010",
   "owner":{  
      "fullName":"Heidi Walker",
      "guid":"I0K38YZZ8FWFYH0JSIPF"
   },
   "status":"OPEN",
   "statusMode":"AUTOMATIC",
   "targetCompletionDateTime":null,
   "template":{  
      "active":null,
      "guid":"6O8RWMNNW3MI1K3M2TOK"
   },
   "type":"Manufacturing"
}
```
Returns an error if the GUID is not valid

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
