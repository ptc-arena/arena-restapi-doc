# GET Quality Process Step Attributes
/settings/qualityprocesses/steps/attributes

Returns    Step Attributes available for Steps  in  Quality Processes. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |

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

## Sample Response Body
Get all Quality Process Step attributes including possible values

GET /settings/qualityprocesses/steps/attributes?includePossibleValues=true

```
{
   "count":48,
   "results":[
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"GYI1KS11YFWEXGZI1KF5",
         "creatable":false,
         "custom":true,
         "defaultValue":"Why 1:\nResponse:\nWhy 2:\nResponse:\nWhy 3:\nResponse:\nWhy 4:\nResponse:\nWhy 5:\nResponse:",
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"GYI1KS11YFWEXGZI1KF5",
         "name":"5 Whys",
         "required":false,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"CUEXGOXXUBSATCVEXGAG",
         "creatable":false,
         "custom":true,
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"CUEXGOXXUBSATCVEXGAG",
         "name":"Action",
         "required":false,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"HZJ2LT22ZGXFYH0J2KMI",
         "creatable":false,
         "custom":true,
         "defaultValue":"Date audit was performed eg. 1 January, 2014",
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"HZJ2LT22ZGXFYH0J2KMI",
         "name":"Audit date",
         "required":false,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"GYI1KS11YFWEXGZI1JLW",
         "creatable":false,
         "custom":true,
         "defaultValue":"List auditors here.",
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"GYI1KS11YFWEXGZI1JLW",
         "name":"Auditor (s)",
         "required":false,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"ASCVEMVVS9Q8RATCVDGH",
         "creatable":false,
         "custom":true,
         "defaultValue":"List controls here.  If there are control documents, attach them as affected objects below.",
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"ASCVEMVVS9Q8RATCVDGH",
         "name":"Controls",
         "required":false,
         "searchable":true
      },
      ...
   ]
}
```
