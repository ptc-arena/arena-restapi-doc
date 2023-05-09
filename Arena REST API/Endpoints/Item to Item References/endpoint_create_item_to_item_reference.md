# POST Item-To-Item Reference Create


/items/&lt;GUID&gt;/items

Creates a new  for an item with a given GUID. 

NOTES:

* Item references are bidirectional.  Creating an Item reference between Items means that that both Items will appear in each others Items view.

* References are not revision controlled or revision specific., and can only be created between released Items. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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
