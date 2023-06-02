# GET Where Used
/items/&lt;GUID&gt;/whereused

Returns an array of Item objects in which the given Item appears as a BOM line, along with the line number and other attributes. Note that when "lineNumber" is null for an assembly line, \(a\) line number generation is set to manual but the user has not yet entered line numbers, or \(b\) line number generation is set to automatic.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
