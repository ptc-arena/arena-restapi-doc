# GET Item Source Relationship


/items/&lt;GUID&gt;/sourcing/&lt;GUID&gt;

Returns a  object with a given GUID for an item with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
