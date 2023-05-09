# GET Supplier Item Attributes


/settings/supplieritems/attributes

Returns   available for Supplier Items. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of the supplier item. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of a supplier item. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting supplier items. |

If this is set to false, it returns only non\-creatable attributes

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all supplier item attributes with possible values included



GET /settings/supplieritems/attributes?includePossibleValues=true

```
{
   "count":13,
   "results":[
      {
         "allowsExplicitNullValue":true,
         "apiName":"L3N6PX663K1J2L4NNT4Z",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"DROP_DOWN",
         "guid":"L3N6PX663K1J2L4NNT4Z",
         "name":"First Article Tester",
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"J1L4NV441IZH0J2LLR20",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"J1L4NV441IZH0J2LLR20",
         "name":"Notes",
         "required":false,
         "searchable":true
      },
      {
         "allowNegatives":false,
         "allowsExplicitNullValue":true,
         "apiName":"K2M5OW552J0I1K3MMS3M",
         "creatable":true,
         "custom":true,
         "decimalPlaces":0,
         "editable":true,
         "fieldType":"NUMBER",
         "guid":"K2M5OW552J0I1K3MMS3M",
         "name":"Stock EOQ",
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"creationDateTime",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"DATETIME",
         "inViews":[
            "SI_SPECS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"creator",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "SI_SPECS"
         ],
         "required":false,
         "searchable":false
      },
      ...
   ]
}
```
