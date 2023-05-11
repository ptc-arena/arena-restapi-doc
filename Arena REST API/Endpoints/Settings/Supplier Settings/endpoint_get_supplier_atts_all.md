# GET Supplier Attributes


/settings/suppliers/attributes

Returns   available for suppliers. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a supplier.<br>If this is set to false, it returns only non\-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a supplier. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting supplier.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
