# GET Change Affected Item
/changes/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a Change Affected Item with a given GUID included in a change with a given GUID. The response includes inventory disposition and information about each view of the item, including whether or not the view is included in the change  and whether or not it contains modifications to the working revision.

* For permanent Changes, when the Item added to the Change is unreleased:

* There is no affectedItemRevision attribute.

* Before the Change is effective, newItemRevision GUID will reference the working  revision of the Item.

* After the Change is effective the new newItemRevision GUID willl reference the Item revision that was made effective as a consequence of this Change.

* newLifecyclePhase is the new lifecycle phase of the Item that was introduced when the Change became effective. 

* newRevisionNumber is the new revision number of the Item specified in the Change that became effective due to the Change being released.

* For permanent Changes, when the Item added to the Change is released:

* Before the Change is effective:

* The newItemRevision GUID references the working revision of the Item. Note this GUID can change if this Item is released by another Change or through a revisioning event.

* The affectedItemRevision GUID references the effective revision of the Item. 

* After the Change is effective:

* The newItemRevision GUID references the Item revision that was made effective as a consequence of this Change.

* The affectedItemRevision GUID references the effective Item revision.

* The newLifecyclePhase is the new lifecycle phase of the Item tas a result of the Change becoming effective.

* The newRevisionNumber is the planned revision number, which becomes the revision number of the Item when the Change becomes effective.

* For temporary Changes:

* Unreleased Items can not be added to a temporary Change. The newLifecyclePhase and newRevisionNumber fields are not used.

* Before the temporary Change is effective, the affectedItemRevision GUID is the effective Item revision.

* After the Deviation becomes effective, the affectedItemRevision GUID is the superseded Item revision. The newItemRevision GUID is the new revision inserted between the former effective and the working revisions.

* After the Deviation, the temporary Change expires, the affectedItemRevision GUID and the newItemRevision GUID do not change.

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
Get a specific  item included in a change

GET /changes/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
   "affectedItemRevision":{
      "effectiveDateTime": "2011-07-26T06:54:20Z",
      "guid":"6O8RAIRRO5O5O29W9CHJ",
      "name": "Front Glass Panel",
      "number":"034-0003",
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
      "effectiveDateTime": "2011-11-18T22:04:06Z",
      "guid":"5N7Q9HQQN4N4N18V889C",
      "name": "Front Glass Panel",
      "number":"034-0003",
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
   "newRevisionNumber": "A",
   "retrainingRequired": true,
   "retraining": "AFTER_APPROVED",
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
