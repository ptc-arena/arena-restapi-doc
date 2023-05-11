# POST Change Affected Item Add


/changes/&lt;GUID&gt;/items

Adds an item to a change with a specific GUID. 

For an overview of the Change Lifecyle in Arena, including a summary of Lifecycle Rules for adding Items to Changes, see .

NOTES:

* newItemRevision is the GUID of the working revision of the Item being added to the change. In workspaces that include Revision Sequences \(wherein the next revision is automatically assigned to an Item as long as no revision has been specified on the working revision\), newRevisionNumber can be omitted, as long as there is a next revision available in the sequence.

* affectedItemRevision is the GUID of the effective revision of the Item being added to the Change.

* The GUID in the response to this call is the Change\-Item association GUID and is used in the PUT Change Affected Item endpoint.

* If includedInThisChange=false for any view, the notes field is not allowed.

* When adding items to a Change with temporary effectivity, no views can be specified. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
Add an item to a change, specifying included views and inventory disposition



/changes/&lt;GUID&gt;/items

```
{
   "filesView":{
      "includedInThisChange":true,
      "notes":"Files notes."
   },
   "sourcingView":{
      "includedInThisChange":true,
      "notes":"Sourcing notes."
   },
   "specsView":{
      "includedInThisChange":true,
      "notes":"Specs notes."
   },
   "bomView":{
      "includedInThisChange":true,
      "notes":"BOM notes."
   },
   "newItemRevision":{
      "guid":"TBVEXAVM9CVCVDN6IAA5"
   },
   "newRevisionNumber":"B",
   "newLifecyclePhase":{
      "guid":"DVFYHUF6TWEH0J2L4EYV"
   },
   "materialEffectivityDateTime":"2018-06-02T00:00:00Z",
   "dispositionAttributes":[
      {
         "guid":"XFZI1EZQDGYL4N5DOHO4",
         "value":"Accept to stock",
         "notes":"Still usable with mod"
      }
   ]
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
```
{
   "affectedItemRevision":{
      "effectiveDateTime": "2020-07-26T06:54:20Z",
      "guid":"8QATCPA1ORARAS2LXQC0",
      "name": "Dura-Glass Panel",
      "number":"130-00001",
      "revisionNumber":"A",
      "revisionStatus": "SUPERSEDED",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/8QATCPA1ORARAS2LXQC0",
          "app": "https://app.bom.com/8QATCPA1ORARAS2LXQC0"
      }
   },
   "bomView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":false,
      "notes":"BOM notes."
   },
   "dispositionAttributes":[
      {
         "guid":"1J3M5I3UHK1J2L3BMFMM",
         "name":"In the Field",
         "notes":null,
         "value":null
      },
      {
         "guid":"2K4N6J4VIL2K3M4CNGNG",
         "name":"WIP",
         "notes":null,
         "value":null
      },
      {
         "guid":"3L5O7K5WJM3L4N5DOHOB",
         "name":"On Order",
         "notes":"Still usable with mod",
         "value":"Accept to stock"
      },
      {
         "guid":"4M6P8L6XKN4M5O6EPIPJ",
         "name":"Finished Goods",
         "notes":null,
         "value":null
      },
      {
         "guid":"5N7Q9M7YLO5N6P7FQJQH",
         "name":"In Stock",
         "notes":null,
         "value":null
      }
   ],
   "filesView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":false,
      "notes":"Files notes."
   },
   "guid":"HZJ2LYJAX0IBUD0C2CRS",
   "materialEffectivityDateTime":null,
   "newItemRevision":{
      "effectiveDateTime": "2020-11-18T22:04:06Z",
      "guid":"TBVEXAVM9CVCVDN6IAA5",
      "name": "Dura-Glass Panel",
      "number":"130-00001",
      "revisionNumber":"B",
      "revisionStatus": "EFFECTIVE",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/TBVEXAVM9CVCVDN6IAA5",
          "app": "https://app.bom.com/TBVEXAVM9CVCVDN6IAA5"
      }
   },
   "newLifecyclePhase":{
      "guid":"DVFYHUF6TWEH0J2L4EYV",
      "name":"In Production"
   },
   "newRevisionNumber":"B",
   "sourcingView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":true,
      "notes":"Sourcing notes."
   },
   "specsView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":false,
      "notes":"Specs notes."
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
