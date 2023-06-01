# PUT Item Update
/items/&lt;GUID&gt;

Updates the metadata of an item with a given GUID. 

Editable attributes: Additional attribute values, category, description, name, offTheShelf, owner, shared, standardCost, targetCost, targetPrice,  uom.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null 

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set description, revisionNumber, standardCost, targetCost, or targetPrice to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

## Sample Request Body
Update description, owner, and additional attributes

```
{
   "additionalAttributes":[
      {
         "guid":"YG0J2AJJGXEWFYHY0FSA",
         "value":[
            "China",
            "Latveria",
            "USA"
         ]
      },
      {
         "guid": "I0K3MU330HYGZI1IKZSB",
         "value": 1000
      }
   ],
   "description":"updated description"
   "owner": {
      "fullName": "James Deckard"
   }   
}
```
Update item number

```
{  
   "numberFormat":{  
      "guid":"DVFY3TUU3AT2L4KLEFBE",
      "fields":[  
         {  
            "apiName":"DVFY3TUU3AT2L4KLEFBE",
            "value":"10-0002-01"
         }
      ]
   }
}
```
Set description of an Item to null.

PUT &lt;url&gt;/items/&lt;GUID&gt;?setnull=true

```
{
   "description": null
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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
```
{
   "additionalAttributes":[
      {
         "apiName":"N5P8RZ885M3L4N6NS8Z0",
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "name":"Material",
         "fieldType":"SINGLE_LINE_TEXT",
         "value":"silicon - non-exempt"
      },
      {
         "apiName":"ZH1K3BKKHYFXGZIZ31DJ",
         "guid":"ZH1K3BKKHYFXGZIZ31DJ",
         "name":"Yearly service check",
         "fieldType":"DATE",
         "value":"2018-12-02T07:59:59Z"
      },
      {
         "apiName":"YG0J2AJJGXEWFYHY0FSA",
         "guid":"YG0J2AJJGXEWFYHY0FSA",
         "multiSelect":true,
         "name":"Affected Countries",
         "fieldType":"FIXED_DROP_DOWN",
         "value":[
            "China",
            "Latveria",
            "USA"
         ]
      },
      {
         "apiName":"I0K3MU330HYGZI1IKZSB",
         "guid":"I0K3MU330HYGZI1IKZSB",
         "name":"Warn when below",
         "fieldType":"NUMBER",
         "value":1000
      }
   ],
   "category":{
      "guid":"P7RAT1AA7O7H0J2J7J83"
   },
   "creationDateTime":"2011-02-11T16:52:40Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"updated description",
   "deviated":false,
   "effectiveDateTime":null,
   "guid":"VDXGZ7GGDUDUDRWY7URV",
   "isAssembly":false,
   "lifecyclePhase":{
      "guid":"BTDWFNWWTASVEXGZIXDY",
      "name":"In Design"
   },
   "modifiedBom":false,
   "modifiedFiles":false,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"Circuit Board, EveryRoad, Model 500",
   "number":"040-0002",
   "offTheShelf":false,
   "owner":{
      "fullName":"James Deckard"
   },
   "procurementType":"MTS",
   "productionCost":null,
   "prototypeCost":null,
   "revisionNumber":null,
   "shared":false,
   "standardCost":null,
   "status":0,
   "supersededDateTime":null,
   "targetCost":null,
   "targetPrice":null,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/VDXGZ7GGDUDUDRWY7URV",
        "app": "https://app.bom.com/VDXGZ7GGDUDUDRWY7URV"
}
```
Response if setnull=true with the appropriate request body.

PUT &lt;url&gt;/items/&lt;GUID&gt;?setnull=true

```
{
   "additionalAttributes":[
      {
         "apiName":"N5P8RZ885M3L4N6NS8Z0",
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "name":"Material",
         "fieldType":"SINGLE_LINE_TEXT",
         "value":"silicon - non-exempt"
      },
      {
         "apiName":"ZH1K3BKKHYFXGZIZ31DJ",
         "guid":"ZH1K3BKKHYFXGZIZ31DJ",
         "name":"Yearly service check",
         "fieldType":"DATE",
         "value":"2018-12-02T07:59:59Z"
      },
      {
         "apiName":"YG0J2AJJGXEWFYHY0FSA",
         "guid":"YG0J2AJJGXEWFYHY0FSA",
         "multiSelect":true,
         "name":"Affected Countries",
         "fieldType":"FIXED_DROP_DOWN",
         "value":[
            "China",
            "Latveria",
            "USA"
         ]
      },
      {
         "apiName":"I0K3MU330HYGZI1IKZSB",
         "guid":"I0K3MU330HYGZI1IKZSB",
         "name":"Warn when below",
         "fieldType":"NUMBER",
         "value":1000
      }
   ],
   "category":{
      "guid":"P7RAT1AA7O7H0J2J7J83"
   },
   "creationDateTime":"2011-02-11T16:52:40Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description": null,
   "deviated":false,
   "effectiveDateTime":null,
   "guid":"VDXGZ7GGDUDUDRWY7URV",
   "isAssembly":false,
   "lifecyclePhase":{
      "guid":"BTDWFNWWTASVEXGZIXDY",
      "name":"In Design"
   },
   "modifiedBom":false,
   "modifiedFiles":false,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"Circuit Board, EveryRoad, Model 500",
   "number":"040-0002",
   "offTheShelf":false,
   "owner":{
      "fullName":"James Deckard"
   },
   "procurementType":"MTS",
   "productionCost":null,
   "prototypeCost":null,
   "revisionNumber":null,
   "shared":false,
   "standardCost":null,
   "status":0,
   "supersededDateTime":null,
   "targetCost":null,
   "targetPrice":null,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/VDXGZ7GGDUDUDRWY7URV",
        "app": "https://app.bom.com/VDXGZ7GGDUDUDRWY7URV"
}
```
Requests return an error if:

* An attribute included in the request is not recognizable. 

```

{  
   "status":400,
   "errors":[  
      {  
         "code":4004,
         "message":"The attribute \"name1\" is not recognized."
      }
   ]
}
```
* The category GUID is not valid.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"J1ICM2LVEXGZIR4\" is not valid."
      }
   ]
}
```
* An option is not valid value for a fixed (non-user-editable) dropdown list.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3006,
         "message":"The specified value \"ea\" is not a valid option for the attribute \"uom\"."
      }
   ]
}
```
* The value exceeds the maximum length for an attribute. 

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3005,
         "message":"The specified value \"1.234567891111111E20\" is too big for the attribute \"productionCost\"."
      }
   ]
}
```
* An improper type of value is given to an attribute. For example if a string value is given to a double attribute.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":400,
         "message":"The format of the request is not valid. Please check the syntax."
      }
   ]
}
```
* One or more additional attributes are not recognized.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3004,
         "message":"The attribute \"custom1637239\" is not recognized."
      }
   ]
}
```
* A number format is invalid.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"FXE8IYHQ9SBUDTLK1\" is not valid."
      }
   ]
}
```
* A required entry for a valid NumberFormat is not given.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3009,
         "message":"The field \"SM Analog Type Code\" is required for the number format \"410-SM Analog  Voltage Regulator\"."
      }
   ]
}
```
* A free text NumberFormat is used, and the given item number exceeds the maximum length.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3015,
         "message":"The given item number is too long. The max length of the free text number format \"FreeText\" is \"10\"."
      }
   ]
}
```
