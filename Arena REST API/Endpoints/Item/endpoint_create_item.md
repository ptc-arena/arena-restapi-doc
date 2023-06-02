# POST Item Create
/items

Creates a new Item object. You can specify no number format, the basic number format, or a valid number format for the workspace \(with or without an auto-generating sequence\), in which case you must specify valid values for each field type in the number format. Each case is shown below.

NOTES:

* The values you specify for attributes must match the attribute types specified in the workspace. For example, when specifying a value for a predefined list, the value must be one of the allowed values.

* Category and other IDs must exist in the workspace.

* A category GUID is required.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
* Create Item with No Number

```
{  
   "category":{  
      "guid":"1J3MRHIIRYHRAT5D1U08"
   },
   "description":"New Part",
   "name":"New Part",
   "offTheShelf":true,
   "owner": {
      "fullName": "James Deckard"
   },
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"A",
   "shared":false,
   "standardCost":3.3,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"Each"
}
```
* Create Item with Autogenerating Number

```
{  
   "category":{  
      "guid":"ZH1K3K3JFSBL4N6O1ZQS"
   },
   "description":"New Part",
   "name":"New Part",
   "numberFormat":{  
      "guid":"L3N6B044Z4NWFYEEF2YCH",
      "fields":[  
         {  
            "guid":"J1L4N4N3ZCV4N6P7QKMR",
            "value":"081"
         }
      ]
   },
   "offTheShelf":true,
   "owner": {
      "fullName": "James Deckard"
   },
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"A",
   "shared":false,
   "standardCost":3.3,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"Each"
}
```
* Create Item with Autogenerating Number and Additional Attributes

When submitting values for Additional Attributes of type NUMBER, the value must be submitted as a number \(not wrapped in quotes.\)

```
{
   "additionalAttributes":[
      {
         "guid":"M4O7QY774L2K3M5MR7YT",
         "value":"5000"
      },
      {
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "value":"Silicon"
      }
   ],
   "category":{
      "guid":"2K4N6ENNK1KUDWFWKWKO"
   },
   "description":"New PCBA",
   "name":"PCBA, EveryHome 2046",
   "numberFormat":{
      "guid":"VDXGZ7GGDUDM5O7OL7R3",
      "fields":[
         {
            "guid":"5N7Q9HQQN4L8RATAIVF4",
            "value":"110"
         }
      ]
   },
   "offTheShelf":true,
   "owner":{
      "fullName":"Heidi Walker"
   },
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"1",
   "shared":false,
   "standardCost":3.3,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"Each"
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Create Item with no number

```
{  
   "additionalAttributes":[  

   ],
   "category":{  
      "guid":"1J3MRHIIRYHRAT5D1U08"
   },
   "creationDateTime":"2017-04-05T22:41:53Z",
   "creator":{  
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"New Part",
   "deviated":false,
   "effectiveDateTime":null,
   "guid":"0I2L4L4KGTCTCQVZVP97",
   "isAssembly":false,
   "lifecyclePhase":{  
      "guid":"BTDWFWFVR4MP8RATCVII",
      "name":"Unreleased"
   },
   "modifiedBom":false,
   "modifiedFiles":false,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"New Part",
   "number":null,
   "offTheShelf":true,
   "owner": {
      "fullName": "James Deckard"
   },
   "procurementType":"MTS",
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"A",
   "shared":false,
   "standardCost":3.3,
   "status":0,
   "supersededDateTime":null,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/0I2L4L4KGTCTCQVZVP97",
        "app": "https://app.bom.com/0I2L4L4KGTCTCQVZVP97"   
}

```
Create Item with Autogenerating Number

```
{  
   "additionalAttributes":[  

   ],
   "category":{  
      "guid":"1J3MRHIIRYHRAT5D1U08"
   },
   "creationDateTime":"2017-04-05T22:41:53Z",
   "creator":{  
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"New Part",
   "deviated":false,
   "effectiveDateTime":null,
   "guid":"0I2L4L4KGTCTCQVZVP97",
   "isAssembly":false,
   "lifecyclePhase":{  
      "guid":"BTDWFWFVR4MP8RATCVII",
      "name":"Unreleased"
   },
   "modifiedBom":false,
   "modifiedFiles":false,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"New Part",
   "number":"10-0002",
   "offTheShelf":true,
   "owner": {
      "fullName": "James Deckard"
   },
   "procurementType":"MTS",
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"A",
   "shared":false,
   "standardCost":3.3,
   "status":0,
   "supersededDateTime":null,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/0I2L4L4KGTCTCQVZVP97",
        "app": "https://app.bom.com/0I2L4L4KGTCTCQVZVP97"
}
```
Create Item with Autogenerating Number and Additional Attributes

```
{
   "additionalAttributes":[
      {
         "apiName":"M4O7QY774L2K3M5MR7YT",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"M4O7QY774L2K3M5MR7YT",
         "name":"MOQ",
         "value":"5000"
      },
      {
         "apiName":"N5P8RZ885M3L4N6NS8Z0",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"N5P8RZ885M3L4N6NS8Z0",
         "name":"Material",
         "value":"Silicon"
      }
   ],
   "category":{
      "guid":"2K4N6ENNK1KUDWFWKWKO"
   },
   "creationDateTime":"2019-02-04T19:49:50Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"New PCBA",
   "deviated":false,
   "effectiveDateTime":null,
   "guid":"9RBUDLUUR8RZIW11GB9L",
   "isAssembly":false,
   "lifecyclePhase":{
      "guid":"6O8RAIRRO5NQ9SBUDS87",
      "name":"Unreleased"
   },
   "modifiedBom":false,
   "modifiedFiles":false,
   "modifiedSourcing":false,
   "modifiedSpecs":true,
   "name":"PCBA, EveryHome 2046",
   "number":"110-0005",
   "offTheShelf":true,
   "owner":{
      "fullName":"Heidi Walker"
   },
   "procurementType":"OTS",
   "productionCost":1.1,
   "prototypeCost":2.2,
   "revisionNumber":"1",
   "shared":false,
   "standardCost":3.3,
   "status":0,
   "supersededDateTime":null,
   "targetCost":4.4,
   "targetPrice":5.5,
   "uom":"each",
   "url": {
        "api": "https://api.arenasolutions.com/v1/items/9RBUDLUUR8RZIW11GB9L",
        "app": "https://app.bom.com/9RBUDLUUR8RZIW11GB9L"
}
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

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
* A required attribute is missing.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3001,
         "message":"The attribute \"uom\" is required."
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
* The category is structural.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3007,
         "message":"This category is structural; objects may not be assigned to it."
      }
   ]
}
```
* The given item number exists in the workspace and the workspace does not allow item number duplication.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3025,
         "message":"A revision of an Item already exists (or has been reserved by an integration) with the item number you selected. Item numbers may not be duplicated in this workspace."
      }
   ]
}
```
