# GET Item Specs


/items/&lt;GUID&gt;

Returns an  object with a given GUID. Note that while the standard practice is to retrieve an item GUID using the GET Items endpoint and then use an item GUID here \(returning the effective revision\), you  can also use a GUID for a specific revision of an item here.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes | true or false | If this is true, the response returns empty additional attributes. The default is false. |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
