# GET Quality Process Summary
/qualityprocesses/&lt;GUID&gt;

Returns a Quality Process object with a specific GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |

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

## Sample Response Body
Get a single quality process

/settings/qualityprocesses/&lt;GUID&gt;

```
{  
   "completedDateTime":null,
   "creationDateTime":"2016-04-19T19:23:22Z",
   "creator":{  
      "fullName":"Roy Stafford",
      "guid":"GYI16WXX6DUDWFYHPRY3"
   },
   "currentStep":{  
      "approvals":null,
      "attributes":null,
      "guid":"HZJ27XYY7EXTCVEXDZ27"
   },
   "description":"New Process Introduction Quality Assurance",
   "guid":"EWGZ4UVV4BUQ9SBUAWZK",
   "name":"New Process Introduction",
   "number":"8D-000001",
   "owner":{  
      "fullName":"Roy Stafford",
      "guid":"GYI16WXX6DUDWFYHPRY3"
   },
   "status":"OPEN",
   "statusMode":"AUTOMATIC",
   "targetCompletionDateTime":"2016-04-30T06:59:59Z",
   "template":{  
      "active":null,
      "guid":"6O8RWMNNW3MI1K3M2TOK"
   },
   "type":null
}
```
Produces an error if the process GUID is not valid.

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
