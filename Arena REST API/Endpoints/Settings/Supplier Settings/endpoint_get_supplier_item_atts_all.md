# GET Supplier Item Attributes
/settings/supplieritems/attributes

Returns  Attributes available for Supplier Items. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of the supplier item.<br>If this is set to false, it returns only non-creatable attributes<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a supplier item. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting supplier items.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
