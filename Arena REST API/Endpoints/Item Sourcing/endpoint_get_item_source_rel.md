# GET Item Source Relationship
/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

Returns a Source Relationship object with a given GUID for an item with a given GUID.

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
Get a source relationship for a given item

/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

```
{  
   "activeProduction":true,
   "activePrototype":false,
   "amlRank":null,
   "amlSplit":null,
   "approved":true,
   "guid":"TBVEJ9AAJQ9DWF0UVMSW",
   "makeItem":false,
   "mfrItem":{  
      "guid":"I0K38YZZ8FY3M55VE9WI"
   },
   "notes":"3/23/2000",
   "vendorItem":{  
      "guid":"I0K38YZZ8FY3M55VE9WI"
   },
   "vendorItemConversionFactor":1
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
      "message": "The guid \"6O8RAIPBRZIZIW2J7TL83\" is not valid."
    }
  ]
}
```
