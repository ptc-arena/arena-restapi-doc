# GET Export Definitions (Search)
/exports?query_string

Returns a collection of Export Definition objects matching the given search criteria.. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all export definitions where results should begin. All export definitions before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | A user defined name for the export. it must be provided on creation and does not need to be unique.<br> |
| number<br> | string<br> | A system generated number starting at 1 and incrementing with each export.<br> |
| description<br> | string<br> | description of the export definition<br> |
| creator.guid<br> | GUID<br> | The unique identifier for the creator of the Export Definition.<br> |
| creator.email<br> | string<br> | The email address of the user account that created the Export Definition.<br> |
| creator.fullName<br> | string<br> | The full name of the user that created the Export Definition.<br> |

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

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
