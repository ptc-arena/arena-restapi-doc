# PUT Request Item Edit


/requests/&lt;GUID&gt;/items/&lt;GUID&gt;

Updates the notes for an item on a request with a given request\-item association GUID, included in a request with a  given GUID.. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
```
{
    "notes": "Edit: This will be affected by the solution."
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
