# POST Quality Process Step Affected Object Add
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

Adds an Affected Object in a step with a given GUID in a Quality Process with a given GUID. The type can be ITEM,   REQUEST, CHANGE, SUPPLIER, SUPPLIER ITEM, FILE, QUALITY,  or URL.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
Add an object of type ITEM

```
{  
   "notes":"Improved venting panel for upcoming release",
   "affected":{  
      "guid":"8S0CH2NXC02JD0CJSFJN"
   }
}
```
Add an object of type REQUEST

```
{
    "notes": "A Request?",
    "affected": {
        "guid": "CUEXGTE5SVEDWFBVUQUK"
    }
}
```
Add an object of type CHANGE

```
{
   "notes":"A Change", 
   "affected":{
     "guid": "ASCV0QST650RAS81FACQ":
   }
}
```
Add an object of type SUPPLIER

```
{
   "notes":"Allied Electronics Inc.", 
   "affected":{
     "guid": "VDXGLBDERQ9FYHMC0ZH6":
   }
}
```
Add an object of type SUPPLIER ITEM

```
{
   "notes":"A Supplier Item", 
   "affected":{
     "guid": "2K4NSIKLYXGL4NLZFKS9":
   }
}
```
Add an object of type File

```
{
   "notes":"A File",
   "affected":{
     "guid":"ZH1KPFHIVUDTCVL9QG9B"
   }
}
```
Add an object of type QUALITY

```
{  
   "notes":"Existing CAPA",
   "affected":{  
      "step":{  
         "guid":"7P9SXNOOX4NJ2L4N1EUS"
      }
   }
}
```
Add an object of type URL

```
{  
   "notes":"look at this!",
   "affected":{  
      "link":"www.flextronics.com",
      "display":"Flextronics home page",
      "description":"Supplier info"
   }
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

## Sample Response Body
add an affected object of type ITEM to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{  
   "affected":{  
      "guid":"8S0CH2NXC02JD0CJSFJN",
      "type":"ITEM"
   },
   "guid":"A89MHQ7ANF001HNAMWIS",
   "notes":"Improved venting panel for upcoming release"
}
```
add an affected object of type REQUEST to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{
    "affected": {
        "guid": "CUEXGTE5SVEDWFBVUQUK",
        "type": "REQUEST"
    },
    "guid": "TBVEXAVM9CU5O7Q8M4FB",
    "notes": "A Request"
}
```
add an affected object of type CHANGE to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{
   "affected": {
       "guid": "ASCV0QST650RAS81FACQ".
       "type": "CHANGE"
   },
   "guid": "EWGZ4UWXA9S07Q9PU9NA",
   "notes": "A Change"
}
```
add an affected object of type SUPPLIER to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{
   "affected": {
       "guid": "VDXGLBDERQ9FYHMC0ZH6".
       "type": "SUPPLIER"
   },
   "guid": "N5P8D356JI1XGZIY3ISG",
   "notes": "Allied Electronics Inc."
}
```
add an affected object of type SUPPLIER ITEM to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{
   "affected": {
       "guid": "2K4NSIKLYXGL4NLZFKS9".
       "type": "SUPPLIER ITEM"
   },
   "guid": "TBVEJ98CP073M50490VI",
   "notes": "A Supplier Item"
}
```
add an affected object of type FILE to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{
   "affected": {
       "guid": "ZH1KPFHIVUDTCVL9QG9B".
       "type": "FILE"
   },
   "guid": "SAUDI8AB0N62L4N38NWU",
   "notes": "A File"
}
```
add an affected object of type QUALITY to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{  
   "affected":{  
      "guid":"LS937AN72907WHU1MLWA",
      "step":{
         "guid":"7P9SXNOOX4NJ2L4N1EUS"
      },
      "type":"QUALITY",
   "guid":"7P9SBJQCS0JFYH0J20O3",
   "notes":"Existing CAPA"
}
```
add an affected object of type URL to a step

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{  
   "affected":{  
      "description":"Supplier info",
      "display":"Flextronics home page",
      "link":"www.flextronics.com",
      "type":"URL"
   },
   "guid":"7P9SBJQCS0JFYH0J20O3",
   "notes":"look at this!"
}
```
Returns an error if a GUID is not valid

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
