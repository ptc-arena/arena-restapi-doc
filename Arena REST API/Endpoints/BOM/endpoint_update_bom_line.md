# PUT BOM Line Update
/items/&lt;GUID&gt;/bom/&lt;GUID&gt;

Updates an existing BOM Line with a given GUID for an item with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Set Null

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| setnull  |   | Append the URL with setnull=true to set refdes or notes to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID  |

## Sample Request Body
PUT /items/&lt;GUID&gt;/bom/&lt;GUID&gt;

```
{  
   "refDes":"u1",
   "quantity":1,
   "notes":"New chip"
}
```
Set a bom attribute to null.

PUT /items/&lt;GUID&gt;/bom/&lt;GUID&gt;?setnull=true

```
{  
   "refDes": null,
}
```
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

## Sample Response Body
Update a BOM line

/items/&lt;GUID&gt;/bom/&lt;GUID&gt;

```
{  
   "additionalAttributes":[  
      {  
         "value":3,
         "name":"Pins",
         "apiName":"custom329",
         "type":"NUMBER"
      }
   ],
   "guid":"O6Q9E44AD9SZI1U6RIAQ",
   "item":{
      "guid":"M4O7C228B7Q7Q50Y5C18"
      "name": "Resistor, 47 Ohm, 1/10W, 5%, 0603, SMD",
      "number": "248-00001",
      "revisionNumber": "C",
      "revisionStatus": "EFFECTIVE",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/M4O7C228B7Q7Q50Y5C18",
          "app": "https://app.arenasolutions.com/M4O7C228B7Q7Q50Y5C18",       },
   },
   "lineNumber":1,
   "notes":"New chip",
   "quantity":1,
   "refDes":"u1"
}
```
Set a BOM attribute to null.

PUT /items/&lt;GUID&gt;/bom/&lt;GUID&gt;?setnull=true

```
{  
   "additionalAttributes":[  
      {  
         "value":3,
         "name":"Pins",
         "apiName":"custom329",
         "type":"NUMBER"
      }
   ],
   "guid":"O6Q9E44AD9SZI1U6RIAQ",
   "item":{
      "guid":"M4O7C228B7Q7Q50Y5C18"
      "name": "Resistor, 47 Ohm, 1/10W, 5%, 0603, SMD",
      "number": "248-00001",
      "revisionNumber": "C",
      "revisionStatus": "EFFECTIVE",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/M4O7C228B7Q7Q50Y5C18",
          "app": "https://app.arenasolutions.com/M4O7C228B7Q7Q50Y5C18",       },
   },
   "lineNumber":1,
   "notes":"New chip",
   "quantity":1,
   "refDes":null
}
```
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
* A reference designator is incorrectly formatted.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3036,
      "message": "Invalid BOM Line: Invalid reference descriptor: c."
    }
  ]
}
```
* A reference designator range is incorrectly formatted.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3036,
      "message": "Invalid BOM Line: Invalid reference designator range: c3-c1."
    }
  ]
}
```
* A reference designator is a duplicate (and reference designator checking is enabled in the workspace)

```
{
  "status": 400,
  "errors": [
    {
      "code": 3036,
      "message": "Invalid BOM Line: Duplicated reference  designators: [c3]."
    }
  ]
}
```
* Quantity does not match number of reference designators (and reference designator checking is enabled in the workspace)

```
{
  "status": 400,
  "errors": [
    {
      "code": 3036,
      "message": "Invalid BOM Line: Quantity (2.0) doesn't match number of reference designators."
    }
  ]
}
```
* The BOM line does not exist.

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
