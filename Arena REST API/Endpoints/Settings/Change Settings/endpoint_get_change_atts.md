# GET Change Attributes
/settings/changes/attributes

Returns  Attributes available for Changes. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |
| creatableOnly  | true or false  | If this is set to true, it returns only creatable attributes, which are settable during creation of a change.If this is set to false, it returns only non-creatable attributes.<br>   |
| editableOnly  | true or false  | If this is set to true, it returns only editable attributes, which are settable during update of a change. The default value is false.  |
| searchableOnly  | true or false  | If this is set to true, it returns only searchable attributes, which are searchable when getting changes.  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all change attributes with possible values included

GET /settings/changes/attributes?includePossibleValues=true

```
{
   "count":26,
   "results":[
      {
         "allowsExplicitNullValue":false,
         "apiName":"ZH1K3BKKHYFXGZI0528P",
         "creatable":true,
         "custom":true,
         "defaultValue":"No",
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "global":true,
         "guid":"ZH1K3BKKHYFXGZI0528P",
         "name":"Cost over $500?",
         "possibleValues":[
            "Yes",
            "No"
         ],
         "required":true,
         "searchable":true
      },
      {
         "allowNegatives":false,
         "allowsExplicitNullValue":false,
         "apiName":"0I2L4CLLIZGYH0J1639I",
         "creatable":true,
         "custom":true,
         "decimalPlaces":0,
         "defaultValue":2,
         "editable":true,
         "fieldType":"NUMBER",
         "global":true,
         "guid":"0I2L4CLLIZGYH0J1639I",
         "name":"Priority (1-5)",
         "required":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"FXH0JR00XEVDWFYGNJQZ",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "global":false,
         "guid":"FXH0JR00XEVDWFYGNJQZ",
         "name":"Urgency",
         "possibleValues":[
            "Critical",
            "High",
            "Medium",
            "Low"
         ],
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"approvalDeadlineDateTime",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"DATETIME",
         "global":true,
         "inViews":[
            "CHANGE_SUMMARY"
         ],
         "required":false,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"canceledDateTime",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"DATETIME",
         "global":true,
         "inViews":[
            "CHANGE_SUMMARY"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"category",
         "creatable":true,
         "custom":false,
         "developerNotes":"Defaults to -uncategorized- if no default is set",
         "editable":true,
         "fieldType":"OBJECT",
         "global":true,
         "guid":"2K4N6ENNK1J6P8RATCVD",
         "inViews":[
            "CHANGE_SUMMARY"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowLowerCase":true,
         "allowNumbers":true,
         "allowUpperCase":true,
         "allowsExplicitNullValue":false,
         "apiName":"description",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "global":true,
         "guid":"1J3M5DMMJ0I5O7Q9SBUV",
         "inViews":[
            "CHANGE_SUMMARY"
         ],
         "maxLength":32000,
         "required":false,
         "searchable":false
      },
      ...
   ]
}
```
