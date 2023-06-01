# PUT Item Source Relationship Update
/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

Updates a Source Relationship object with a given GUID for an item with a given GUID. Note that updating a source relationship  modifies the existing Source Relationship GUID on the working revision.

## Request Headers

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set notes, amlRank, or amlSplit to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

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
