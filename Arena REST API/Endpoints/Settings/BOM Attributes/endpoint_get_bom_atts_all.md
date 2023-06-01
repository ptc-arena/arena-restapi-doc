# GET BOM Attributes
/settings/items/bom/attributes

Returns    Attributes available for BOMs. 
          
        

Inactive attributes are not returned.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a BOM.<br>If this is set to false, it returns only non-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a BOM. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting BOMs.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> |   | Number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
