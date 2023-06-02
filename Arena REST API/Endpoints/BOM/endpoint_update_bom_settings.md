# PUT BOM Settings Update
/items/&lt;GUID&gt;/bom/settings

Updates BOM Settings for the BOM of an Item with a given GUID. The two settings available for BOMs are:

* automaticallyGenerateLineNumbers

* checkReferenceDesignators

You can edit one or both settings with the same request.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
/items/ASCVEMVVS9S9S6D0DDZ5/bom/settings

```
{  
   "automaticallyGenerateLineNumbers":false
}
```
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
Update BOM settings

/items/ASCVEMVVS9S9S6D0DDZ5/bom/settings

```
{  
   " automaticallyGenerateLineNumbers ":false,
   " checkReferenceDesignators ":true
}
```
Request with bad GUID

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
