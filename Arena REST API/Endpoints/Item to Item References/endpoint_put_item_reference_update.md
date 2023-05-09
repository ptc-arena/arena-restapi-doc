# PUT Item-To-Item Reference Update


/items/&lt;GUID&gt;/items/&lt;GUID&gt;

Updates the metadata of an Item\-To\-Item reference with a given GUID

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set notes to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

## Sample Request Body
PUT /items/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "note": "update notes"
}
```
PUT /items/&lt;GUID&gt;/items/&lt;GUID&gt;?setnull=true

```
{
    "note": null
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

## Sample Responses
Update a given Item\-To\-Item Reference.



/items/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "TBVEXAVM9CTFYH0IXE17",
    "item": {
        "guid": "R9TCV8TK7AT1KZNA8V1W"
    },
    "note": "update notes"
}
```
Set an Item to Item attribute to null

PUT /items/&lt;GUID&gt;/items/&lt;GUID&gt;?setnull=true

```
{
    "guid": "TBVEXAVM9CTFYH0IXE17",
    "item": {
        "guid": "R9TCV8TK7AT1KZNA8V1W"
    },
    "note": null
}
```
Returns an error if:

* the format of the request is incorrect:

```
{
  "status": 400,
  "errors": [
    {
      "code": 400,
      "message": "The format of the request is not valid. Please check the syntax."
    }
  ]
}
```
* a GUID is invalid:

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"X9TCV8TK7AT1KZNA8V1Q\" is not valid."
    }
  ]
}
```
