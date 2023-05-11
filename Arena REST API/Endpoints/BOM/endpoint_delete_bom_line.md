# DELETE BOM Line


/items/&lt;GUID&gt;/bom/&lt;GUID&gt;

Deletes a BOM Line with a given GUID from an Item with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 204<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
No JSON response. 

An error is returned if:

* The user does not have access to the Item they are trying to add to a BOM.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3024,
      "message": "Either you do not have privileges to access the requested data or it does not exist."
    }
  ]
}
```
* The BOM is locked to editing by inclusion on a locked Change/locked by a Change Admin.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3034,
      "message": "The item is locked."
    }
  ]
}
```
* The BOM Line does not exist.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3024,
      "message": "Either you do not have privileges to access the  requested data or it does not exist."
    }
  ]
}
```
