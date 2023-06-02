# GET Item-To-Item Reference
/items/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns an    Item reference  with a given GUID for an item with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
