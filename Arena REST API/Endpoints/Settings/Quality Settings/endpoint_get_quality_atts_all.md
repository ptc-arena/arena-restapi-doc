# GET Quality Process Attributes


/settings/qualityprocesses/attributes

Returns      available for the Summary view of Quality Processes.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of a quality process. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of a quality process. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting quality processes. |

If this is set to false, it returns only non\-creatable attributes.

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
Get all Quality Process summary attributes including possible values



GET /settings/qualityprocesses/attributes?includePossibleValues=true

```
{
   "count":14,
   "results":[
      {
         "allowsExplicitNullValue":false,
         "apiName":"completedDateTime",
         "creatable":false,
         "editable":false,
         "fieldType":"DATETIME",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"creationDateTime",
         "creatable":false,
         "editable":false,
         "fieldType":"DATETIME",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"creator",
         "creatable":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"currentStep",
         "creatable":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"description",
         "creatable":true,
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "maxLength":4000,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"guid",
         "creatable":false,
         "editable":false,
         "fieldType":"GUID",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"name",
         "creatable":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "maxLength":200,
         "required":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"number",
         "creatable":false,
         "editable":false,
         "fieldType":"SINGLE_LINE_TEXT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"owner",
         "creatable":true,
         "defaultValue":"Settings/Quality/Templates/Default Owner",
         "editable":true,
         "fieldType":"OBJECT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"status",
         "creatable":false,
         "editable":false,
         "fieldType":"FIXED_DROP_DOWN",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "possibleValues":[
            "OPEN",
            "COMPLETED"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"statusMode",
         "creatable":false,
         "editable":false,
         "fieldType":"FIXED_DROP_DOWN",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "possibleValues":[
            "MANUAL",
            "AUTOMATIC"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"targetCompletionDateTime",
         "creatable":true,
         "editable":true,
         "fieldType":"DATETIME",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"template",
         "creatable":true,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "required":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"type",
         "creatable":true,
         "editable":true,
         "fieldType":"DROP_DOWN",
         "inViews":[
            "QUALITY_SUMMARY"
         ],
         "possibleValues":[
            "Critical",
            "Low",
            "Normal"
         ],
         "required":false,
         "searchable":true
      }
   ]
}
```
