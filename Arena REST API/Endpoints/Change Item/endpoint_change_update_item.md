# PUT Change Affected Item Edit


/changes/&lt;GUID&gt;/items/&lt;GUID&gt;

Updates modification information for an item on a change with a given change\-item association GUID, included in a change with a  given GUID, including  item views/notes, new revision number, new lifecycle phase, and inventory disposition information. 

Item modifications can only be edited while a change is in the Open and Unlocked lifecycle phase. As soon as a change is submitted, all included Items are locked to modification.

When making edits to an Item's modification information, you  provide  newRevisionNumber, even if you do not wish to change it from the current value.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{
   "filesView":{
      "includedInThisChange":false
   },
   "sourcingView":{
      "includedInThisChange":false
   },
   "specsView":{
      "includedInThisChange":true,
      "notes":"note new owner"
   },
   "bomView":{
      "includedInThisChange":true,
      "notes":"modifications at lines 17 and 34"
   },
   "newRevisionNumber":"C",
   "newLifecyclePhase":{
      "guid":"O6Q9S07T9HZ2L4N6P38C"
   },
   "materialEffectivityDateTime":"2017-06-03T19:23:58Z",
   "dispositionAttributes":[
      {
         "guid":"6O8RAIPBRZGYH0J0206J",
         "value":"Use to exhaust",
         "notes":"The remaining batches can be shipped with the service bulletin"
      }
   ]
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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
Update the modification information for an item on a change



/changes/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
   "affectedItemRevision":{
      "effectiveDateTime": "2020-10-01T06:54:20Z",
      "guid":"YG0J2J2IERARATB537OW",
      "name": "Power Supply",
      "number":"110-0003",
      "revisionNumber":"A",
      "revisionStatus": "SUPERSEDED",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/YG0J2J2IERARATB537OW",
          "app": "https://app.bom.com/YG0J2J2IERARATB537OW"
      }
   },
   "bomView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":true,
      "notes":"modifications at lines 17 and 34"
   },
   "dispositionAttributes":[
      {
         "guid":"Q8SBUBUA6J0I1K3MH6FR",
         "name":"On Order",
         "notes":null,
         "value":null
      },
      {
         "guid":"R9TCVCVB7K1J2L4NI7GB",
         "name":"WIP",
         "notes":null,
         "value":null
      },
      {
         "guid":"TBVEXEXD9M3L4N6PK9HS",
         "name":"Finished Goods",
         "notes":null,
         "value":null
      },
      {
         "guid":"UCWFYFYEAN4M5O7QLAI3",
         "name":"In the Field",
         "notes":null,
         "value":null
      },
      {
         "guid":"6O8RAIPBRZGYH0J0206J",
         "name":"In Stock",
         "notes":"The remaining batches can be shipped with the service bulletin",
         "value":"Use to exhaust"
      }
   ],
   "filesView":{
      "includedInThisChange":false
   },
   "guid":"UCWFYFYEAN5YH0JSFPEP",
   "materialEffectivityDateTime":2017-06-03T19:23:58Z,
   "newItemRevision":{
      "effectiveDateTime": "2020-11-18T22:04:06Z",
      "guid":"3L5O7O7NJWFWFYGA8CTT",
      "name": "Power Supply",
      "number":"110-0003",
      "revisionNumber":"B",
      "revisionStatus": "EFFECTIVE",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/3L5O7O7NJWFWFYGA8CTT",
          "app": "https://app.bom.com/3L5O7O7NJWFWFYGA8CTT"
      }
   },
   "newLifecyclePhase":{
      "guid":"O6Q9S07T9HZ2L4N6P38C",
      "name":"In Production"
   },
   "newRevisionNumber":"C",
   "sourcingView":{
      "includedInThisChange":false
   },
   "specsView":{
      "includedInThisChange":true,
      "lockedByAnotherChange":false,
      "modifiedOnWorkingRev":false,
      "notes":"note new owner"
   }
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
