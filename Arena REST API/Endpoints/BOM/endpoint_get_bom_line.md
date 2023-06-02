# GET BOM Line
/items/&lt;GUID&gt;/bom/&lt;GUID&gt;

Returns a BOM Line object with a given GUID, the immediate child of an assembly with a given GUID \(with no filters.\) 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/x-www-form-urlencoded  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes  | true or false  | If this is true, the response returns empty additional attributes. The default is false.  |
| includeBomSubstitutes  | true or false  | if this is true, the response returns BOM Substitutes  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  |   |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get BOM line \(including empty additional attributes\)

/items/ASCVEMVVS9S9S6D0DDZ5/bom/WEYH08HHEVEL4N6F52SC?includeEmptyAdditionalAttributes=true

```
{
   "additionalAttributes":[
      {
         "apiName":"custom325",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"4M6P8GPPM3K2L4N6P8I6",
         "name":"Bin #",
         "value":null
      }
   ],
   "guid":"YG0J2AJJGXGN6P8H74SP",
   "item":{
      "guid":"K2M5OW552J2AT7E1EHJN"
      "name": "Bezel, Side, EveryHome",
      "number": "248-00001",
      "revisionNumber": "C",
      "revisionStatus": "EFFECTIVE",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/K2M5OW552J2AT7E1EHJN",
          "app": "https://app.arenasolutions.com/K2M5OW552J2AT7E1EHJN",  
      },
   },
   "lineNumber":null,
   "notes":null,
   "quantity":1,
   "refDes":null
}
```
Get BOM line \(include any BOM Substitutes\)

/items/&lt;GUID&gt;/bom/&lt;GUID&gt;?includeBomSubstitutes=true

```
{
    "guid": "WEG45O7EXG7QK9SD",
    "item": {
        "guid": "I02QRAT1KZPMDPDW",
        "number": "T78-437-99431",
        "revisionNumber": "A",
        "name": "Capacitor, Tantalum, 10uF@16V, B pkg",
        "revisionStatus" : "Working",
        "url": {
                "api": "https://api.arenasolutions.com/v1/items/I02QRAT1KZPMDPDW",
                "app": "https://app.arenasolutions.com/I02QRAT1KZPMDPDW",  
        },                                         
    },
    "lineNumber": 8,
    "notes": "BOM notes",
    "quantity": 1,
    "refDes": "J1"
    "additionalAttributes": [
        {
            "apiName": "2KMABUBTCVEXGZIF",
            "fieldType": "NUMBER",
            "guid": "2KMABUBTCVEXGZIF",
            "name": "Classification",
            "value": 1
        },
        ...
    ],
    "substitutes": [ 
        {
            "guid": "M4O7LIMOZGZ7Q5TUPZDB",
            "item": {
                "guid": "J1L4IFJLWDW3M5WM1UTZ",
                "number": "T78-437-98442",
                "revisionNumber": "A",
                "name": "Capacitor, Tantalum, 10uF@24V, B pkg",
                "revisionStatus" : "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/I02QRAT1KZPMDPDW",
                    "app": "https://app.arenasolutions.com/I02QRAT1KZPMDPDW",  
                },                         
            }
            "notes": "A substitute",
            "quantity": 1,
            "rank": 2
        },
        ...
    ]
}
```
Request with a bad GUID.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"WEYH08HHEVEL4N6F52Sf\" is not valid."
    }
  ]
}
```
