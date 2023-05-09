# PUT Item Source Relationship Update


/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

Updates a  object with a given GUID for an item with a given GUID. Note that updating a source relationship  modifies the existing Source Relationship GUID on the working revision.

## Request Headers

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set notes, amlRank, or amlSplit to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

## Sample Request Body
PUT /items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

```
{  
   "amlRank":2
}
```
PUT /items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;?setnull=true

```
{  
   "amlRank":null
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
Update a source relationship for a given item



/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

```
{  
   "activeProduction":false,
   "activePrototype":false,
   "amlRank":2,
   "amlSplit":null,
   "approved":true,
   "guid":"I0K38YU3B6PTCVG5OV8P",
   "makeItem":false,
   "mfrItem":{  
      "guid":"ASCV0QMV3YHM5OOAA1AL"
   },
   "notes":"api-sourcing-relationship1",
   "vendorItem":{  
      "guid":"3L5OTJFOWRAFYHH33U59"
   },
   "vendorItemConversionFactor":2
}
```
Set an Item Sourcing attribute to null

PUT /items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;?setnull=true

```
{  
   "activeProduction":false,
   "activePrototype":false,
   "amlRank":null,
   "amlSplit":null,
   "approved":true,
   "guid":"I0K38YU3B6PTCVG5OV8P",
   "makeItem":false,
   "mfrItem":{  
      "guid":"ASCV0QMV3YHM5OOAA1AL"
   },
   "notes":"api-sourcing-relationship1",
   "vendorItem":{  
      "guid":"3L5OTJFOWRAFYHH33U59"
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
* a general error occurs:

```
{
  "status": 400,
  "errors": [
    {
      "code": 4000,
      "message": "Sorry, a system error occurred, please try again."
    }
  ]
}
```
