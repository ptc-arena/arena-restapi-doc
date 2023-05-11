# GET Change Item Attributes


/settings/changes/items/attributes

Returns   \(including inventory disposition\) available for Changes. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during the addition of an item to a change.<br>If this is set to false, it returns only non\-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during updates to a change\-item relationship. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting changes\-item associations.<br> |

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
Get all modified item attributes, showing all possible values



GET /settings/changes/items/attributes?includePossibleValues=true

```
{
   "count":14,
   "results":[
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom4168105",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"CUEXGOXXUBTGZI1IKR6B",
         "name":"Finished Goods",
         "possibleValues":[
            "N/A",
            "Ship-as-is",
            "Rework",
            "Scrap",
            "See Notes"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom4168107",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"EWGZIQZZWDVI1K3KMT8M",
         "name":"In Stock",
         "possibleValues":[
            "N/A",
            "Build-out",
            "Rework",
            "Scrap",
            "See Notes"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom4168106",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"DVFYHPYYVCUH0J2JLS71",
         "name":"In the Field",
         "possibleValues":[
            "N/A",
            "Do Nothing",
            "Notify",
            "Rework",
            "Recall",
            "See Notes"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom4168103",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ASCVEMVVS9REXGZGIP4A",
         "name":"On Order",
         "possibleValues":[
            "N/A",
            "Accept to stock",
            "Cancel",
            "Scrap",
            "See Notes"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom2269737",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"9RBUDLUUR8QDWFYGNJQP",
         "name":"Urgency",
         "possibleValues":[
            "Critical",
            "High",
            "Medium",
            "Low"
         ],
         "required":true,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"custom4168104",
         "creatable":true,
         "custom":true,
         "editable":true,
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"BTDWFNWWTASFYH0HJQ5Q",
         "name":"WIP",
         "possibleValues":[
            "N/A",
            "Build-out",
            "Rework",
            "Scrap",
            "See Notes"
         ],
         "required":false,
         "searchable":true
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"affectedItemRevision",
         "creatable":true,
         "custom":false,
         "developerNotes":"Item Revision that is affected",
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "required":true,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"bomView",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"filesView",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":true,
         "apiName":"materialEffectivityDateTime",
         "creatable":true,
         "custom":false,
         "editable":true,
         "fieldType":"DATETIME",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "required":false,
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"newItemRevision",
         "creatable":false,
         "custom":false,
         "developerNotes":"Item Revision to be made effective",
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"newLifecyclePhase",
         "creatable":true,
         "custom":false,
         "developerNotes":"New Revision for effective item",
         "editable":true,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"sourcingView",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      },
      {
         "allowsExplicitNullValue":false,
         "apiName":"specsView",
         "creatable":false,
         "custom":false,
         "editable":false,
         "fieldType":"OBJECT",
         "inViews":[
            "CHANGE_ITEMS"
         ],
         "searchable":false
      }
   ]
}
```
