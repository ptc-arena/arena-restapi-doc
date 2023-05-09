# GET Export Definitions (Search)


/exports?query_string

Returns a collection of Export Definition objects matching the given search criteria.. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all export definitions where results should begin. All export definitions before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| name | string | A user defined name for the export. it must be provided on creation and does not need to be unique. |
| number | string | A system generated number starting at 1 and incrementing with each export.  |
| description | string | description of the export definition |
| creator.guid | GUID | The unique identifier for the creator of the Export Definition. |
| creator.email | string | The email address of the user account that created the Export Definition. |
| creator.fullName | string | The full name of the user that created the Export Definition. |

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

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
Get all export definitions



GET /exports

```
{  
   "count": 3,
   "results":[  
      {  
         "creationDateTime": "2020-03-09T21:17:44Z"  
         "creator": {
             "email": "hwalker@everyroadgps.com",
             "fullName": "Heidi Walker",
             "guid": "WEYH0DYPCFWFYH0JSIPD"
         },
         "criteria": [
             [
                 {
                     "attribute": "number",
                     "value": "900-00001",
                     "operator": "IS_EQUAL_TO"
                 }
             ]
         ],
         "description": "March 9",
         "guid": "L3N6P2NE14K3M5JYNZFB",
         "name": "Model 300",
         "number": 1,
         "options": {
             "bomLevels": "NONE",
             "exportViews": [
                 "SPECS",
                 "BOM",
                 "FILES"
             ],
             "header": "name",
             "revisionStatus": "POTENTIAL",
             "format": "csv"
         },
         "world": "ITEMS"
      },
      {  
         "creationDateTime": "2020-03-10T17:08:27Z"  
         "creator": {
             "email": "hwalker@everyroadgps.com",
             "fullName": "Heidi Walker",
             "guid": "WEYH0DYPCFWFYH0JSIPD"
         },
         "criteria": [
             [
                 {
                     "attribute": "number",
                     "value": "900-00001",
                     "operator": "IS_EQUAL_TO"
                 }
             ]
         ],
         "description": "Test Export Definition",
         "guid": "SAUDW9UL8BRATCQ5U6HL",
         "name": "Potential Model 300",
         "number": 2,
         "options": {
             "bomLevels": "NONE",
             "exportViews": [
                 "SPECS",
                 "BOM",
                 "FILES"
             ],
             "header":"apiName",
             "revisionStatus": "POTENTIAL",
             "format": "csv"
         },
         "world": "ITEMS"
      },
      {  
         "creationDateTime": "2020-03-10T17:30:17Z"  
         "creator": {
             "email": "hwalker@everyroadgps.com",
             "fullName": "Heidi Walker",
             "guid": "WEYH0DYPCFWFYH0JSIPD"
         },
         "criteria": [
             [
                 {
                     "attribute": "number",
                     "value": "800-000300",
                     "operator": "IS_EQUAL_TO"
                 }
             ]
         ],
         "description": "800 Export Definition",
         "guid": "TBVEXAVM9CSBUDR6V7IW",
         "name": "800 BOM Export",
         "number": 3,
         "options": {
             "bomLevels": "FULL",
             "exportViews": [
                 "SPECS",
                 "BOM",
                 "FILES"
             ],
             "header":"apiName",
             "revisionStatus": "LATEST",
             "format": "json"
         },
         "world": "ITEMS"
      },
}
```
Get export definitions named "EFFECTIVE PCBAs"



GET &lt;url&gt;/export?name=EFFECTIVE PCBAs

```
{
    "count": 3,
    "results": [
        {
            "creationDateTime": "2020-03-10T21:15:04Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "criteria": [
                [
                    {
                        "attribute": "number",
                        "value": "8",
                        "operator": "STARTS_WITH"
                    }
                ]
            ],
            "description": "Effective Revision of 8 series",
            "guid": "WEYH0DYPCFVEXGU9YALQ",
            "name": "EFFECTIVE PCBAs",
            "number": 4,
            "options": {
                "bomLevels": "FULL",
                "exportViews": [
                    "SPECS",
                    "BOM",
                    "FILES"
                ],
                "fileContent": {
                    "item": "PRIMARY",
                    "supplierItem": "NONE"
                },
                "header": "apiName",
                "revisionStatus": "LATEST",
                "format": "csv"
            },
            "world": "ITEMS"
        },
        {
            "creationDateTime": "2020-03-10T21:18:54Z",
            "creator": {
                "email": "ecanard@everyroadgps.com",
                "fullName": "Eleanor Canard",
                "guid": "1J3M5I3UHK1K3M5OXNUV"
            },
            "criteria": [
                [
                    {
                        "attribute": "number",
                        "value": "8",
                        "operator": "STARTS_WITH"
                    }
                ]
            ],
            "description": "Effective Revision of 8 series",
            "guid": "XFZI1EZQDGWFYHVAZBMU",
            "name": "EFFECTIVE PCBAs",
            "number": 5,
            "options": {
                "bomLevels": "FULL",
                "exportViews": [
                    "SPECS",
                    "BOM",
                    "FILES"
                ],
                "fileContent": {
                    "item": "PRIMARY",
                    "supplierItem": "NONE"
                },
                "header": "name",
                "revisionStatus": "LATEST",
                "format": "csv"
            },
            "world": "ITEMS"
        },
        {
            "creationDateTime": "2020-03-10T21:19:14Z",
            "creator": {
                "email": "ecanard@everyroadgps.com",
                "fullName": "Eleanor Canard",
                "guid": "1J3M5I3UHK1K3M5OXNUV"
            },
            "criteria": [
                [
                    {
                        "attribute": "number",
                        "value": "9",
                        "operator": "STARTS_WITH"
                    }
                ]
            ],
            "description": "Effective Revision of 9 series",
            "guid": "YG0J2F0REHXGZIWB0CNE",
            "name": "EFFECTIVE PCBAs",
            "number": 6,
            "options": {
                "bomLevels": "FULL",
                "exportViews": [
                    "SPECS",
                    "BOM",
                    "FILES"
                ],
                "fileContent": {
                    "item": "PRIMARY",
                    "supplierItem": "NONE"
                },
                "header": "apiName",
                "revisionStatus": "LATEST",
                "format": "csv"
            },
            "world": "ITEMS"
        }
    ]
}
```
Request with an invalid search attribute.

GET /export?creator.Name=Heidi Walker

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3019,
         "message":"The attribute \"creator.Name\" is not searchable."
      }
   ]
}
```
