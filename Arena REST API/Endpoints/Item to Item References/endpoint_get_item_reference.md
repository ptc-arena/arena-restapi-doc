# GET Item-To-Item Reference
/items/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns an    Item reference  with a given GUID for an item with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

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
Get an Item Reference for a given item

/items/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "0I2LQGHHQXGXGVRR5XND",
    "item": {
        "guid": "ASCV0QRR07Q7Q511F7V0",
    },
    "notes": "the notes"
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
