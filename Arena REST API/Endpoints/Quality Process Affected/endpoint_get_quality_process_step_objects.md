# GET Quality Process Step Affected Objects


/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

Returns a collection  of  for a step with a given GUID in a Quality Process with a given GUID.

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

## Sample Response Body
Get affected objects for a quality process step



/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/affected

```
{  
   "count":4,
   "results":[  
      {  
         "affected":{  
            "description":"supplier info",
            "display":"Flextronics",
            "link":"www.flextronics.com",
            "type":"URL"
         },
         "guid":"5N7Q9HOAQYHDWFYH0YMJ",
         "notes":"Flextronics home page"
      },
      {  
         "affected":{  
            "guid":"K2M5OW3P5DWSBUDWFCNT",
            "step":{  
               "guid":"L3N6PX4Q6EXTCVEXGDOY"
            },
            "type":"QUALITY"
         },
         "guid":"P7RAT18UAI1XGZI1KI7E",
         "notes":null
      },
      {  
         "affected":{  
            "guid":"XFZI19G2IQ9Q9SBHKVAP",
            "type":"ITEM"
         },
         "guid":"N5P8RZ6S8GZVEXGZIG5A",
         "notes":null
      },
      {  
         "affected":{  
            "guid":"GYI1KSZL19SRAQT1RNH7",
            "type":"REQUEST"
         },
         "guid":"VDXGZ7E0GO73M5O7QODM",
         "notes":null
      },
            {  
         "affected":{  
            "guid":"FXH0JWH8VYHK3ML98YSK",
            "type":"CHANGE"
         },
         "guid":"7P9SBO90NQ9J2L0778WO",
         "notes":null
      }
   ]
}
```
Returns an error if the GUID is not valid

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
