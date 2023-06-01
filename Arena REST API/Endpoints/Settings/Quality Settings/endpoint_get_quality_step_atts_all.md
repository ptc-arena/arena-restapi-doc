# GET Quality Process Step Attributes
/settings/qualityprocesses/steps/attributes

Returns    Step Attributes available for Steps  in  Quality Processes. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |

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
