# GET BOM
/items/&lt;GUID&gt;/bom

Returns an array of BOM Line objects, the immediate children of an assembly with a given GUID \(with no filters.\) 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includeAdditionalAttributes<br> | true or false<br> | If this is true, the response includes additional attributes for each BOM Line. The default is false.<br> |

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

## Sample Responses Body
Get the BOM of an Item with a specific GUID

/items/ASCVEMVVS9S9S6D0DDZ5/bom

```
{  
   "count":40,
   "results":[  
      {  
         "guid":"P7RAF566FM5CVE8ZLBJ5",
         "item":{  
            "guid":"ASCV0QRR07Q7Q511F8Z3",
            "name": "Bezel, Front, EveryRoad",
            "number": "432-00001",
            "revisionNumber": "C",
            "revisionStatus": "EFFECTIVE",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/ASCV0QRR07Q7Q511F8Z3",
                "app": "https://app.arenasolutions.com/ASCV0QRR07Q7Q511F8Z3", 
            },
         },
         "lineNumber":1,
         "notes":null,
         "quantity":5,
         "refDes":"C15,C6,C10-12"
      },
      {  
         "guid":"3L5OTJKKT0JQ9SMDZP5Z",
         "item":{  
            "guid":"Q8SBG677GN6N6LHHVP7Y",
            "name": "Bezel, Front, EveryRoad",
            "number": "432-00001",
            "revisionNumber": "C",
            "revisionStatus": "EFFECTIVE",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/Q8SBG677GN6N6LHHVP7Y",
                "app": "https://app.arenasolutions.com/Q8SBG677GN6N6LHHVP7Y", 
            },
         },
         "lineNumber":2,
         "notes":null,
         "quantity":1,
         "refDes":"C3"
      },
      {  
         "guid":"4M6PUKLLU1KRATNE0Q4O",
         "item":{  
            "guid":"VDXGLBCCLSBSBQMM0UZ1"
            "name": "Side Bezel, Front, EveryRoad",
            "number": "432-00005",
            "revisionNumber": "C",
            "revisionStatus": "EFFECTIVE",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/VDXGLBCCLSBSBQMM0UZ1",
                "app": "https://app.arenasolutions.com/VDXGLBCCLSBSBQMM0UZ1", 
            },
         },
         "lineNumber":3,
         "notes":null,
         "quantity":3,
         "refDes":"C9,C13-14"
      },
      …
   ]
}
```
GET the BOM line of an Item with a specific GUID. Also get any BOM Attributes \(also known as Additional Attributes\).

GET /items/6O8RWMQP21KSBQL/bom?includeAdditionalAttributes=true

```
{
    "count": 4,
    "results": [
        {
            "additionalAttributes": [
                {
                    "apiName": "GYI16WYZCBSATCVEXGP9",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "GYI16WYZCBSATCVEXGP9",
                    "name": "BOMATT",
                    "value": "Ultra Violet"
                },
                {
                    "apiName": "N5P8D356JIZH0J2L4N3H",
                    "fieldType": "DATE",
                    "guid": "N5P8D356JIZH0J2L4N3H",
                    "name": "DOCK DATE",
                    "value": "20220603235959"
                }
            ],
            "guid": "N5P8D356JI18RA3H96F9",
            "item": {
                "guid": "M4O7C245IH08R617NZJU",
                "name": "Child Jamaica",
                "number": "449-2020369",
                "revisionNumber": "1",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/M4O7C245IH08R617NZJU",
                    "app": "https://app.bom.com/M4O7C245IH08R617NZJU"
                }
            },
            "lineNumber": 0,
            "notes": null,
            "quantity": 1,
            "refDes": null
        },
        {
            "additionalAttributes": [
                {
                    "apiName": "GYI16WYZCBSATCVEXGP9",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "GYI16WYZCBSATCVEXGP9",
                    "name": "BOMATT",
                    "value": "Infared"
                },
                {
                    "apiName": "N5P8D356JIZH0J2L4N3H",
                    "fieldType": "DATE",
                    "guid": "N5P8D356JIZH0J2L4N3H",
                    "name": "DOCK DATE",
                    "value": "20220603235959"
                }
            ],
            "guid": "TBVEJ9BCPO7EXG9PWXPC",
            "item": {
                "guid": "BTDW1RTU76PXGVQ6X798",
                "name": "Child Queensbridge",
                "number": "337-989656",
                "revisionNumber": "1",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/BTDW1RTU76PXGVQ6X798",
                    "app": "https://app.bom.com/BTDW1RTU76PXGVQ6X798"
                }
            },
            "lineNumber": 0,
            "notes": null,
            "quantity": 1,
            "refDes": null
        },
        {
            "additionalAttributes": [
                {
                    "apiName": "GYI16WYZCBSATCVEXGP9",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "GYI16WYZCBSATCVEXGP9",
                    "name": "BOMATT",
                    "value": "Cerulean"
                },
                {
                    "apiName": "N5P8D356JIZH0J2L4N3H",
                    "fieldType": "DATE",
                    "guid": "N5P8D356JIZH0J2L4N3H",
                    "name": "DOCK DATE",
                    "value": "20220603235959"
                }
            ],
            "guid": "UCWFKACDQP8FYHAQXYQQ",
            "item": {
                "guid": "WEYHMCEFSRAI1GBRISTA",
                "name": "Child Astoria",
                "number": "989-2020369",
                "revisionNumber": "1",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/WEYHMCEFSRAI1GBRISTA",
                    "app": "https://app.bom.com/WEYHMCEFSRAI1GBRISTA"
                }
            },
            "lineNumber": 1,
            "notes": null,
            "quantity": 1,
            "refDes": null
        },
        {
            "additionalAttributes": [
                {
                    "apiName": "GYI16WYZCBSATCVEXGP9",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "GYI16WYZCBSATCVEXGP9",
                    "name": "BOMATT",
                    "value": "Azure"
                },
                {
                    "apiName": "N5P8D356JIZH0J2L4N3H",
                    "fieldType": "DATE",
                    "guid": "N5P8D356JIZH0J2L4N3H",
                    "name": "DOCK DATE",
                    "value": "20220603235959"
                }
            ],
            "guid": "8QATYOQR43MTCVO4BC4Q",
            "item": {
                "guid": "WEYHMCEFSRAI1GBL3Z90",
                "name": "Five Points",
                "number": "379-0369",
                "revisionNumber": "2",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/WEYHMCEFSRAI1GBL3Z90",
                    "app": "https://app.bom.com/WEYHMCEFSRAI1GBL3Z90"
                }
            },
            "lineNumber": 0,
            "notes": null,
            "quantity": 1,
            "refDes": null
        }
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
         "message":"The guid \"ASCVEMVVS9S9S6D0DDZ3\" is not valid."
      }
   ]
}
```
