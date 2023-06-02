# PUT Quality Process Step Affected Object Update
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected/&lt;GUID&gt;

Updates an existing Affected Object with a given GUID in a step with a given GUID in a Quality Process with a given GUID.  Current supported Affected Objects are ITEMS, CHANGES, SUPPLIERS, SUPPLIER ITEMS, FILES, QUALITY, and URLs.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
```
{  
   "notes":"look at this!"
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
