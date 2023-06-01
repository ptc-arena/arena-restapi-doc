# GET Item Attributes
/settings/items/attributes

/settings/items/attributes/&lt;GUID&gt;

Returns  Attributes available for Items. By adding a valid Item Attribute GUID at the end of the URL, the endpoint returns a single unique Item attribute.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which can be set during creation of an item.<br>If this is set to false, it returns only non-creatable sattributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which can be set during update of an item. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting items.<br> |

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
Get all item attributes with possible values included

GET /settings/items/attributes?includePossibleValues=true

```
{
   "count":51,
   "results":[
      {
         "allowsExplicitNullValue":true,
         "apiName":"DVFYHPYYVCTBUDWDIYP0",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"DVFYHPYYVCTBUDWDIYP0",
         "name":"Capacitance",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"UCWFY6FFCTA2L4N6P7AM",
         "costCalculation":"ROLLUP",
         "creatable":true,
         "currency":"USD",
         "custom":true,
         "decimalPlaces":2,
         "editable":true,
         "fieldType":"COST",
         "global":true,
         "guid":"UCWFY6FFCTA2L4N6P7AM",
         "name":"Cost Option A",
         "private":false,
         "required":false,
         "revisionControlled":false,
         "searchable":true
      },
      {
         "active":true,
         "allowsExplicitNullValue":true,
         "apiName":"VDXGZ7GGDUB3M5O7Q8BS",
         "costCalculation":"ROLLUP",
         "creatable":true,
         "currency":"USD",
         "custom":true,
         "decimalPlaces":2,
         "editable":true,
         "fieldType":"COST",
         "global":true,
         "guid":"VDXGZ7GGDUB3M5O7Q8BS",
         "name":"Cost Option B",
         "private":false,
         "required":false,
         "revisionControlled":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"EWGZIQZZWDUCVEXEJZQF",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"EWGZIQZZWDUCVEXEJZQF",
         "name":"Current",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"FXH0JR00XEVDWFYFK0R2",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"FXH0JR00XEVDWFYFK0R2",
         "name":"Diameter",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"HZJ2LT22ZGXFYH0HM2TN",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"HZJ2LT22ZGXFYH0HM2TN",
         "name":"EOQ",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"K2M5OW552J0I1K3KP5WX",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "global":false,
         "guid":"K2M5OW552J0I1K3KP5WX",
         "maxSelections":10,
         "multiSelect":true,
         "name":"Head Type",
         "possibleValues":[
            "Pan",
            "Round",
            "Binding",
            "Fillister",
            "One way",
            "Slat and oval",
            "Square",
            "Indented hexagonal",
            "Indented hexagonal washer",
            "Hexagonal",
            "Hex flange"
         ],
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"L3N6PX663K1J2L4LQ6XP",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"L3N6PX663K1J2L4LQ6XP",
         "name":"Length",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"M4O7QY774L2K3M5MR7YT",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"M4O7QY774L2K3M5MR7YT",
         "name":"MOQ",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"N5P8RZ885M3L4N6NS8Z0",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "name":"Material",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"O6Q9S0996N4M5O7OT90B",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"O6Q9S0996N4M5O7OT90B",
         "name":"Package",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"Q8SBU2BB8P6O7Q9QVB2N",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"Q8SBU2BB8P6O7Q9QVB2N",
         "name":"Power",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"R9TCV3CC9Q7P8RARWC3A",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "global":false,
         "guid":"R9TCV3CC9Q7P8RARWC3A",
         "name":"Resistance",
         "revisionControlled":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"ZH1K3BKKHYFXGZIZ31DJ",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"DATE",
         "global":false,
         "guid":"ZH1K3BKKHYFXGZIZ31DJ",
         "name":"Yearly service check",
         "revisionControlled":true,
         "searchable":true
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
         "guid":"R9TCV3CC9Q8VEXGZI1K0",
         "inViews":[
            "ITEM_SPECS"
         ],
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
         "global":true,
         "inViews":[
            "ITEM_SPECS"
         ],
         "searchable":false
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
         "excludedValues":[
            ";",
            "-"
         ],
         "fieldType":"MULTI_LINE_TEXT",
         "global":true,
         "guid":"SAUDW4DDAR9WFYH0J2LG",
         "inViews":[
            "ITEM_SPECS"
         ],
         "maxLength":255,
         "required":false,
         "searchable":true
      },
      ...
   ]
}
```
Get a single Item attribute with a specific GUID.

GET /settings/items/attributes/EWGZIVG7UXEWFYFE0DQN

```
{
    "allowsExplicitNullValue": true,
    "apiName": "EWGZIVG7UXEWFYFE0DQN",
    "creatable": true,
    "custom": true,
    "editable": true,
    "example": "100pF",
    "fieldType": "SINGLE_LINE_TEXT",
    "global": false,
    "guid": "EWGZIVG7UXEWFYFE0DQN",
    "maxLength": 1000,
    "name": "Capacitance",
    "revisionControlled": true,
    "searchable": true,
    "visibleWhenBlank": false
}
```
