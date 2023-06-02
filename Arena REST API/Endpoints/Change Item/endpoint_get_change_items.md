# GET Change Affected Items
/changes/&lt;GUID&gt;/items

Returns all Change Affected Items included in a change with a given GUID. The response includes inventory dispostion and information about each view of each item, including whether it is included in the change and whether it contains modifications to the working revision.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
Get all items included in a change

GET /changes/&lt;GUID&gt;/items

```
{
   "count":4,
   "results":[         
      {
         "affectedItemRevision":{
            "effectiveDateTime": "2011-07-26T06:54:20Z",
            "guid":"Q8SBU2BB8P8P8MTGTWBE",
            "name": "Yellow, Side Fastener",
            "number":"072-0003",
            "revisionNumber":"A",
            "revisionStatus": "SUPERSEDED",
            "url": {
               "api": "https://api.arenasolutions.com/v1/items/Q8SBU2BB8P8P8MTGTWBE",
               "app": "https://app.bom.com/Q8SBU2BB8P8P8MTGTWBE"
            }
         },
         "bomView":{
            "includedInThisChange":false,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         },
         "dispositionAttributes":[
            {
               "guid":"GYI1KS11YFWEXGZGIP4U",
               "name":"On Order",
               "notes":null,
               "value":null
            },
            {
               "guid":"HZJ2LT22ZGXFYH0HJQ5B",
               "name":"WIP",
               "notes":null,
               "value":null
            },
            {
               "guid":"I0K3MU330HYGZI1IKR6T",
               "name":"Finished Goods",
               "notes":null,
               "value":null
            },
            {
               "guid":"J1L4NV441IZH0J2JLS78",
               "name":"In the Field",
               "notes":null,
               "value":null
            },
            {
               "guid":"K2M5OW552J0I1K3KMT84",
               "name":"In Stock",
               "notes":null,
               "value":null
            }
         ],
         "filesView":{
            "includedInThisChange":false,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         },
         "guid":"J1L4NV441I0TCVENB6LQ",
         "materialEffectivityDateTime":null,
         "newItemRevision":{
            "effectiveDateTime": "2011-11-18T22:04:06Z",
            "guid":"L3N6PX663K3K3HOBOO3A",
            "name": "Yellow, Side Fastener",
            "number":"072-0003",
            "revisionNumber":"B",
            "revisionStatus": "EFFECTIVE",
            "url": {
               "api": "https://api.arenasolutions.com/v1/items/L3N6PX663K3K3HOBOO3A",
               "app": "https://app.bom.com/L3N6PX663K3K3HOBOO3A"
            }
         },
         "newLifecyclePhase":{
            "guid":"ASCVEMVVS9RUDWFYHWC3",
            "name":"In Production"
         },
         "newRevisionNumber": "B",
         "retrainingRequired": true,
         "retraining": "AFTER_EFFECTIVE",
         "sourcingView":{
            "includedInThisChange":true,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         },
         "specsView":{
            "includedInThisChange":true,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         }
      },
      {
         "affectedItemRevision":{
            "effectiveDateTime": "2011-10-26T07:54:20Z",
            "guid":"6O8RAIRRO5O5O29W9CHJ",
            "name": "Blue, Side Fastener",
            "number":"072-0005",
            "revisionNumber":"A",
            "revisionStatus": "SUPERSEDED",
            "url": {
               "api": "https://api.arenasolutions.com/v1/items/6O8RAIRRO5O5O29W9CHJ",
               "app": "https://app.bom.com/6O8RAIRRO5O5O29W9CHJ"
            }
         },
         "bomView":{
            "includedInThisChange":false,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         },
         "dispositionAttributes":[
            {
               "guid":"GYI1KS11YFWEXGZGIP4U",
               "name":"On Order",
               "notes":null,
               "value":"Cancel"
            },
            {
               "guid":"HZJ2LT22ZGXFYH0HJQ5B",
               "name":"WIP",
               "notes":null,
               "value":"Build-out"
            },
            {
               "guid":"I0K3MU330HYGZI1IKR6T",
               "name":"Finished Goods",
               "notes":null,
               "value":"Ship-as-is"
            },
            {
               "guid":"J1L4NV441IZH0J2JLS78",
               "name":"In the Field",
               "notes":null,
               "value":"Do Nothing"
            },
            {
               "guid":"K2M5OW552J0I1K3KMT84",
               "name":"In Stock",
               "notes":"use to exhaust",
               "value":"Build-out"
            }
         ],
         "filesView":{
            "includedInThisChange":true,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":true,
            "notes":null
         },
         "guid":"L3N6PX663K2VEXGPD8NB",
         "materialEffectivityDateTime":null,
         "newItemRevision":{
            "effectiveDateTime": "2011-12-25T22:04:06Z",
            "guid":"5N7Q9HQQN4N4N18V889C",
            "name": "Blue, Side Fastener",
            "number":"072-0005",
            "revisionNumber":"B",
            "revisionStatus": "EFFECTIVE",
            "url": {
               "api": "https://api.arenasolutions.com/v1/items/5N7Q9HQQN4N4N18V889C",
               "app": "https://app.bom.com/5N7Q9HQQN4N4N18V889C"
            }
         },
         "newLifecyclePhase":{
            "guid":"9RBUDLUUR8QTCVEXGVB9",
            "name":"Abandoned"
         },
         "newRevisionNumber": "2",
         "retrainingRequired": true,
         "retraining": "AFTER_EFFECTIVE",    
         "sourcingView":{
            "includedInThisChange":false,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":false,
            "notes":null
         },
         "specsView":{
            "includedInThisChange":true,
            "lockedByAnotherChange":false,
            "modifiedOnWorkingRev":true,
            "notes":null
         }
      },
      ...
   ]
}
```
Request with invalid GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
