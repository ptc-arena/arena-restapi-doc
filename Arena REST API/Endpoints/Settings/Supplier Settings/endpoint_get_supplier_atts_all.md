# GET Supplier Attributes


/settings/suppliers/attributes

Returns   available for suppliers. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of a supplier. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of a supplier. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting supplier. |

If this is set to false, it returns only non\-creatable attributes.

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
Get all supplier attributes with possible values included



GET /settings/suppliers/attributes?includePossibleValues=true

```
{
   "count":14,
   "results":[
      {
         "allowsExplicitNullValue":true,
         "apiName":"HZJ2LT22ZGXFYH0J8J6T",
         "creatable":true,
         "custom":true,
         "defaultValue":"No",
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"HZJ2LT22ZGXFYH0J8J6T",
         "name":"At-Risk Supplier?",
         "possibleValues":[
            "Yes",
            "No"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowNegatives":false,
         "allowsExplicitNullValue":false,
         "apiName":"O6Q9S0996N4M5O7QFORI",
         "creatable":true,
         "custom":true,
         "decimalPlaces":1,
         "defaultValue":10,
         "editable":true,
         "fieldType":"NUMBER",
         "guid":"O6Q9S0996N4M5O7QFORI",
         "name":"Rating 1-10",
         "required":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"I0K3MU330HYGZI1K9K72",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"DATE",
         "guid":"I0K3MU330HYGZI1K9K72",
         "name":"Re-Evaluate On",
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"accountNumber",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "inViews":[
            "SUPPLIER_PROFILE"
         ],
         "maxLength":40,
         "required":false,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"addresses",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"OBJECT",
         "inViews":[
            "SUPPLIER_PROFILE"
         ],
         "required":false,
         "searchable":false
      },
      ...
   ]
}
```
