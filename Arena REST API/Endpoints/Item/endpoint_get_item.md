# GET Item Specs


/items/&lt;GUID&gt;

Returns an  object with a given GUID. Note that while the standard practice is to retrieve an item GUID using the GET Items endpoint and then use an item GUID here \(returning the effective revision\), you  can also use a GUID for a specific revision of an item here.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes<br> | true or false<br> | If this is true, the response returns empty additional attributes. The default is false.<br> |
| responseview<br> | string<br> | Allows users to customize the scope and size of the response data. Possible values and definitions:<br> <br> * minimum \- returns the GUID, item number, and url.<br><br> * compact \- returns the commen set of data that includes some core attrinutes in addition to the attributes returned in the minimum response.<br><br> * full \- returns the complete set of data including custom attributes.<br> |

* minimum \- returns the GUID, item number, and url.

* compact \- returns the common set of data that includes some core attrinutes in addition to the attributes returned in the minimum response.

* full \- returns the complete set of data including custom attributes.

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
Get a single item \(including empty additional attributes\).



GET /items/GUID?includeEmptyAdditionalAttributes=true

```
{
   "additionalAttributes":[
      {
         "apiName":"1I35WWQQSEKPOHOKXUMU",
         "fieldType":"NUMBER",
         "guid":"1I35WWQQSEKPOHOKXUMU",
         "name":"EOQ",
         "value":1000
      },
      {
         "apiName":"N5P8RZ885M3L4N6NS8Z0",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "name":"Material",
         "value":"silicon - non-exempt"
      },
      {
         "apiName":"ZH1K3BKKHYFXGZIZ31DJ",
         "fieldType":"DATE",
         "guid":"ZH1K3BKKHYFXGZIZ31DJ",
         "name":"Yearly service check",
         "value":"2018-12-02T07:59:59Z"
      },
      {
         "apiName":"YG0J2AJJGXEWFYHY0FSA",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"YG0J2AJJGXEWFYHY0FSA",
         "multiSelect":true,
         "name":"Affected Countries",
         "value":[
            "China",
            "Latveria",
            "USA"
         ]
      }
   ],
   "assemblyType": "ASSEMBLY",
   "category":{
      "guid":"P7RAT1AA7O7H0J2J7J83",
      "name": "Assembly"
   },
   "creationDateTime":"2011-02-11T16:52:40Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
      "guid": "DVFY3SVCSJOJ2L4N38F
   },
   "description":"Circuit board for the EveryRoad product - Model 500",
   "deviated":false,
   "effectiveDateTime":"2018-04-06T22:33:27Z",
   "guid":"L3N6PX663K3K3HOBOOT0",
   "isAssembly": true,
   "inAssembly": true.
   "lifecyclePhase":{
      "guid":"BTDWFNWWTASVEXGZIXDY",
      "name":"In Design"
   },
   "modifiedBom":false,
   "modifiedFiles":true,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"Circuit Board, EveryRoad, Model 500",
   "number":"040-0002",
   "offTheShelf":false,
   "owner":{
      "fullName":"John Parker"
   },
   "procurementType":"OTS",
   "productionCost":null,
   "prototypeCost":null,
   "revisionNumber":"2",
   "shared":true,
   "standardCost":null,
   "status":1,
   "supersededDateTime":null,
   "targetCost":null,
   "targetPrice":null,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/L3N6PX663K3K3HOBOOT0",
        "app": "https://app.bom.com/L3N6PX663K3K3HOBOOT0"
}
```
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
