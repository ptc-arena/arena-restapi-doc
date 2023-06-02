# GET Quality Process Step Affected Object
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected/&lt;GUID&gt;

Returns an Affected Object with a given GUID that appears in a step with a given GUID in a Quality Process with a given GUID.

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
