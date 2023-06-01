# GET BOM Line
/items/&lt;GUID&gt;/bom/&lt;GUID&gt;

Returns a BOM Line object with a given GUID, the immediate child of an assembly with a given GUID \(with no filters.\) 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/x-www-form-urlencoded<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes<br> | true or false<br> | If this is true, the response returns empty additional attributes. The default is false.<br> |
| includeBomSubstitutes<br> | true or false<br> | if this is true, the response returns BOM Substitutes<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> |   |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
