# GET BOM Settings


/items/&lt;GUID&gt;/bom/settings

Returns BOM Settings for the BOM of an Item with a given GUID. The two settings available for BOMs are:

* automaticallyGenerateLineNumbers \(true/false\)

* checkReferenceDesignators \(true/false\)

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get BOM settings



/items/ASCVEMVVS9S9S6D0DDZ5/bom/settings

```
{  
   "automaticallyGenerateLineNumbers":true,
   "checkReferenceDesignators":true
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"ASCVEMVVS9S9S6D0DDZ51\" is not valid."
    }
  ]
}
```
