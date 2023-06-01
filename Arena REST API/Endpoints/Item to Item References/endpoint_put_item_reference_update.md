# PUT Item-To-Item Reference Update
/items/&lt;GUID&gt;/items/&lt;GUID&gt;

Updates the metadata of an Item-To-Item reference with a given GUID

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set notes to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

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

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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

## Sample Responses
Update a given Item-To-Item Reference.

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
