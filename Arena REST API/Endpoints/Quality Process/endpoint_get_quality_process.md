# GET Quality Process Summary
/qualityprocesses/&lt;GUID&gt;

Returns a Quality Process object with a specific GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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
