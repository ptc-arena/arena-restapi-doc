# POST BOM Line Create


/items/&lt;GUID&gt;/bom

Creates a new  for an item with a given GUID. A BOMLine consists of an item and the reference designator, quantity, and notes that appear on its line in a BOM.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
Add BOM Line

```
{  
   "refDes":"R3-R5",
   "quantity":3,
   "notes":"BOM Notes",
   "item":{  
      "guid":"L3N6PX663K3K3HOBORNT"
   }
}
```
Add BOM Line with Additional Attribute

```
{  
   "additionalAttributes":[  
      {  
         "guid": "VZJ875P0VFCDDOFMHRMW",
         "value": 3001
      }
   ],
   "refDes":"R3-R5",
   "quantity":3,
   "notes":"some notes",
   "item":{  
      "guid":"L3N6PX663K3K3HOBORNT"
   }
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

## Sample Response Body
Add BOM line with additional attribute



/items/&lt;GUID&gt;/bom

```
{  
   "additionalAttributes":[  
      {  
         "value":"3001",
         "name":"Stocking Bin",
         "apiName":"Stocking Bin",
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
   "notes":"some notes",
   "quantity":3,
   "refDes":"R3-R5"
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
* User trying to add superseded revision to BOM \(only effective revision can be added\)

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"ASCVEMVVS9S9S6D0DDZ51\" is not valid."
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
* A reference designator is a duplicate \(and reference designator checking is enabled in the workspace\)

```
{
  "status": 400,
  "errors": [
    {
      "code": 3036,
      "message": "Invalid BOM Line: Duplicated reference designators: [c3]."
    }
  ]
}
```
* Quantity does not match number of reference designators \(and reference designator checking is enabled in the workspace\)

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
