# POST Item Source Relationship Create
/items/&lt;GUID&gt;/sourcing

Creates a new Source Relationship for an item with a given GUID. Note that you can create two different types of source relationship:
          
          
        

* In a direct relationship, you get a manufacturer Item directly from the manufacturer. The manufacturer and vendor items are the same. You can also specify a Make-Item relationship (where your own company makes the part) by setting MakeItem to True.


* In an indirect relationship, you buy a manufacturer item from a vendor. The manufacturer and vendor items are different. You can choose not to specify the manufacturer or vendor item in an indirect source relationship, to create an "any" relationship \(source to any manufacturer or vendor.\)


NOTES:
          
          
          
        

* The suppliers and supplier items named in the source relationship must already exist in the workspace. Find their GUIDs with Get Supplier and Get Supplier Item requests.

* The values you specify for attributes must match the attribute types specified in the workspace. For example, when specifying a value for a predefined list, the value must be one of the allowed values.

* Number values must appear in quotation marks.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
* Create Indirect Source Relationship

```
{  
   "amlRank":2,
   "approved":true,
   "mfrItem":{  
      "guid":" FXH05VR083MRATTHJD8A "
   },
   "notes":"api-sourcing-relationship1",
   "vendorItem":{  
      "guid":" BTDW1RNW4ZIN6PPBP28X"
   },
   "vendorItemConversionFactor":2,
   "makeItem":false
}
```
* Create Direct Source Relationship (note that the mfrItem and vendorItem GUIDs are the same)

```
{  
   "amlRank":2,
   "approved":true,
   "mfrItem":{  
      "guid":" FXH05VR083MRATTHJD8A "
   },
   "notes":"api-sourcing-relationship1",
   "vendorItem":{  
      "guid":" FXH05VR083MRATTHJD8A "
   },
   "vendorItemConversionFactor":2,
   "makeItem":false
}
```
* Create Make-Item Source Relationship (where your company makes the Item)

```
{  
   "amlRank":2,
   "approved":true,
   "notes":"api-sourcing-relationship1",
   "vendorItemConversionFactor":null,
   "makeItem":true
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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
Create a new source relationship for a given item

/items/&lt;GUID&gt;/sourcing

```
{  
   "activeProduction":false,
   "activePrototype":false,
   "amlRank":2,
   "amlSplit":null,
   "approved":true,
   "creationDateTime":null,
   "guid":"EWGZ4UQZ72LP8RC2ZDXS",
   "makeItem":false,
   "mfrItem":{  
      "guid":"BTDW1RNW4ZIN6PPBP28X"
   },
   "notes":"api-sourcing-relationship1",
   "offTheShelf":false,
   "vendorItem":{  
      "guid":"BTDW1RNW4ZIN6PPBP28X"
   },
   "vendorItemConversionFactor":2
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
* the vendorItemConversionFactor attribute is not null in a Make-Item Source Relationship or when there is no Vendor Item:

```
{
  "status": 400,
  "errors": [
    {
      "code": 3040,
      "message": "Conversion factor must be null if no vendor item or is make myself."
    }
  ]
}
```
