# PUT Quality Process Step Affected Object Update
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected/&lt;GUID&gt;

Updates an existing Affected Object with a given GUID in a step with a given GUID in a Quality Process with a given GUID.  Current supported Affected Objects are ITEMS, CHANGES, SUPPLIERS, SUPPLIER ITEMS, FILES, QUALITY, and URLs.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "notes":"look at this!"
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
Update an affected object in a quality process step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;step_GUID&gt;/affected/&lt;GUID&gt;

```
{  
   "affected":{  
      "description":"Supplier info",
      "display":"Flextronics home page",
      "link":"www.flextronics.com",
      "type":"URL"
   },
   "guid":"7P9SBJQCS0JFYH0J20O3",
   "notes":"look at this!"
}
```
Returns an error if a GUID is not valid

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
