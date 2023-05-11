# GET Quality Process Attributes


/settings/qualityprocesses/attributes

Returns      available for the Summary view of Quality Processes.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a quality process.<br>If this is set to false, it returns only non\-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a quality process. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting quality processes.<br> |

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
