# GET Where Used


/items/&lt;GUID&gt;/whereused

Returns an array of  objects in which the given Item appears as a BOM line, along with the line number and other attributes. Note that when "lineNumber" is null for an assembly line, \(a\) line number generation is set to manual but the user has not yet entered line numbers, or \(b\) line number generation is set to automatic.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
Get where used results for an item



/items/&lt;GUID&gt;/whereused

```
{  
   "count":2,
   "results":[  
      {  
         "guid":"I0K3MU1N3BU1K3MU8IT0",
         "item":{  
            "guid":"M4O7QY5R7FYFYCILCQJX"
            "name": "Resistor, 43 Ohm",
            "number": "248-00031",
            "revisionNumber": "C",
            "revisionStatus": "EFFECTIVE",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/M4O7QY5R7FYFYCILCQJX",
                "app": "https://app.arenasolutions.com/M4O7QY5R7FYFYCILCQJX" 
            }

         },
         "lineNumber":4,
         "notes":"paren 1 child 1",
         "quantity":1,
         "refDes":"c3"
      },
      {  
         "guid":"J1L4NV2O4CV2L4NV9JUI",
         "item":{  
            "guid":"WEYH08F1HP8P8MSVM0T4"
            "name": "Resistor, 50 Ohm",
            "number": "248-00033",
            "revisionNumber": "C",
            "revisionStatus": "EFFECTIVE",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/WEYH08F1HP8P8MSVM0T4",
                "app": "https://app.arenasolutions.com/WEYH08F1HP8P8MSVM0T4" 
            }
         },
         "lineNumber":null,
         "notes":"paren 1 child 1",
         "quantity":1,
         "refDes":"c3"
      }
   ]
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"I0K3MU1N3BU1K3MU8IT0\" is not valid."
    }
  ]
}
```
