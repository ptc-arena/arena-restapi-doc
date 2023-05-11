# POST Item-To-Item Reference Create


/items/&lt;GUID&gt;/items

Creates a new  for an item with a given GUID. 

NOTES:

* Item references are bidirectional.  Creating an Item reference between Items means that that both Items will appear in each others Items view.

* References are not revision controlled or revision specific., and can only be created between released Items. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
* Create Item\-To\-Item Reference

```
{
   "item": {
      "guid": "R9TCV8TK7AT1KZNA8V1W"
   },
   "note": "Item Reference Notes"
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Responses
Create a new Item\-to\-Item reference.



/items/&lt;GUID&gt;/items

```
{
   "guid": "TBVEXAVM9CTFYH0IXE17",
   "item": {
      "guid": "R9TCV8TK7AT1KZNA8V1W"
      },
   "note": "Item Reference Notes"
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
* the GUID is not valid:

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"R9TCV8TK7AT1KZNA8V1Y\" is not valid."
    }
  ]
}

```
