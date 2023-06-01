# GET Quality Process Step Affected Object
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected/&lt;GUID&gt;

Returns an Affected Object with a given GUID that appears in a step with a given GUID in a Quality Process with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

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
Get a single affected object from a quality process step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected/&lt;GUID&gt;

```
{  
   "affected":{  
      "description":"Supplier info",
      "display":"Flextronics home page",
      "link":"www.flextronics.com",
      "type":"URL"
   },
   "guid":"5N7Q9HOAQYHDWFYH0YMJ",
   "notes":"Flex page"
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
