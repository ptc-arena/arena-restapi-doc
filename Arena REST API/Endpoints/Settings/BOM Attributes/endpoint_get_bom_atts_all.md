# GET BOM Attributes


/settings/items/bom/attributes

Returns     available for BOMs. 

Inactive attributes are not returned.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of a BOM. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of a BOM. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting BOMs. |

If this is set to false, it returns only non\-creatable attributes.

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length |   | Number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all BOM attributes with possible values included



GET /settings/items/bom/attributes?includePossibleValues=true

```
{
   "count":7,
   "results":[
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"4M6P8GPPM3K2L4N6P8I6",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"4M6P8GPPM3K2L4N6P8I6",
         "name":"Bin #",
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"guid",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"GUID",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"item",
         "creatable":true,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "required":true,
         "searchable":false
      },
      {
         "allowNegatives":false,
         "allowsExplicitNullValue":false,
         "apiName":"lineNumber",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"NUMBER",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "maxValue":9999,
         "required":false,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"notes",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"MULTI_LINE_TEXT",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "maxLength":4000,
         "required":false,
         "searchable":false
      },
      {
         "allowNegatives":false,
         "allowsExplicitNullValue":false,
         "apiName":"quantity",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"NUMBER",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "maxValue":1000000,
         "required":true,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"refDes",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "inViews":[
            "ITEM_BOM",
            "ITEM_WHEREUSED"
         ],
         "maxLength":32000,
         "required":false,
         "searchable":false
      }
   ]
}
```
