# GET Item Source Relationships
/items/&lt;GUID&gt;/sourcing

Returns an array of Source Relationship objects for an item with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all source relationships where results should begin. All relationships before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the maximum number of returned results. The default value \(no specified limit\) is 20, the maximum is 400.  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Headers

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Responses
Get all source relationships for an item, limit results to 25

GET /items/Q8SBU2BB8P8P8MTGTTHH/sourcing?limit=25

```
{  
   "count":5,
   "results":[  
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
      },
      {  
         "activeProduction":false,
         "activePrototype":true,
         "amlRank":null,
         "amlSplit":null,
         "approved":true,
         "guid":"UCWFKABBKRAEXG1VWNTK",
         "makeItem":false,
         "mfrItem":{  
            "guid":"J1L49Z009GZ4N66WFAXA"
         },
         "notes":"4/17/2000",
         "vendorItem":{  
            "guid":"J1L49Z009GZ4N66WFAXA"
         },
         "vendorItemConversionFactor":1
      },
      {  
         "activeProduction":false,
         "activePrototype":false,
         "amlRank":null,
         "amlSplit":null,
         "approved":false,
         "guid":"VDXGLBCCLSBFYH2WXOUN",
         "makeItem":false,
         "mfrItem":{  
            "guid":"K2M5A011AH05O77XGBYE"
         },
         "notes":"Disapproved for repeated late delivery.",
         "vendorItem":{  
            "guid":"K2M5A011AH05O77XGBYE"
         },
         "vendorItemConversionFactor":1
      },
      {  
         "activeProduction":false,
         "activePrototype":false,
         "amlRank":null,
         "amlSplit":null,
         "approved":true,
         "guid":"WEYHMCDDMTCGZI3XYPVB",
         "makeItem":false,
         "mfrItem":{  
            "guid":"L3N6B122BI16P88YHCZ9"
         },
         "notes":"The relationship has been re-approved. The new factory is now online and the parts are approved.",
         "vendorItem":{  
            "guid":"L3N6B122BI16P88YHCZ9"
         },
         "vendorItemConversionFactor":1
      },
      {  
         "activeProduction":false,
         "activePrototype":false,
         "amlRank":null,
         "amlSplit":null,
         "approved":true,
         "guid":"ZH1KPFGGPWFJ2L601SYY",
         "makeItem":false,
         "mfrItem":{  
            "guid":"M4O7C233CJ27Q99ZID0U"
         },
         "notes":"Adding Trilby as our main source.",
         "vendorItem":{  
            "guid":"M4O7C233CJ27Q99ZID0U"
         },
         "vendorItemConversionFactor":1
      }
   ]
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
* the Item GUID is invalid:

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
