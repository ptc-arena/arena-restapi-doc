# GET Change Item Attributes
/settings/changes/items/attributes

Returns  Attributes \(including inventory disposition\) available for Changes. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |
| creatableOnly  | true or false  | If this is set to true, it returns only creatable attributes, which are settable during the addition of an item to a change.If this is set to false, it returns only non-creatable attributes.<br>   |
| editableOnly  | true or false  | If this is set to true, it returns only editable attributes, which are settable during updates to a change-item relationship. The default value is false.  |
| searchableOnly  | true or false  | If this is set to true, it returns only searchable attributes, which are searchable when getting changes-item associations.  |

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
