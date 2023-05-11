# PUT BOM Settings Update


/items/&lt;GUID&gt;/bom/settings

Updates BOM Settings for the BOM of an Item with a given GUID. The two settings available for BOMs are:

* automaticallyGenerateLineNumbers

* checkReferenceDesignators

You can edit one or both settings with the same request.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body


/items/ASCVEMVVS9S9S6D0DDZ5/bom/settings

```
{  
   "automaticallyGenerateLineNumbers":false
}
```
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
