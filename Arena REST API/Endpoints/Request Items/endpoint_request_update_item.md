# PUT Request Item Edit


/requests/&lt;GUID&gt;/items/&lt;GUID&gt;

Updates the notes for an item on a request with a given request\-item association GUID, included in a request with a  given GUID.. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{
    "notes": "Edit: This will be affected by the solution."
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
Update the notes information for an item on a request



/requests/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "CUEXGTE5SV87Q9A3DB9W",
    "item": {
        "guid": "R9TCV8TK7AT1KZNA8V5I",
        "name": "Gasket, 3.75 in",
        "number": "437-00002",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/R9TCV8TK7AT1KZNA8V5I",
            "app": "https://app.bom.com/R9TCV8TK7AT1KZNA8V5I"
        }
    },
    "notes": "Edit: This will be affected by the solution."
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
