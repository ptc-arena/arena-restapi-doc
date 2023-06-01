# GET Import Definitions (Search)
/imports?query_string

Returns a collection of Import Definition objects matching the given search criteria.. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all import definitions where results should begin. All import definitions before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | A user defined name for the import definition. it must be provided on creation and does not need to be unique.<br> |
| number<br> | string<br> | A system generated number starting at 1 and incrementing with each export.<br> |
| description<br> | string<br> | description of the import definition<br> |
| creator.guid<br> | GUID<br> | The unique identifier for the creator of the Export Definition.<br> |
| creator.email<br> | string<br> | The email address of the user account that created the import Definition.<br> |
| creator.fullName<br> | string<br> | The full name of the user that created the Import Definition.<br> |
| mode<br> | string<br> | The Mode of the import. The mode dictates the function of the import.<br> |

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
Get all import definitions that use Item Specs as a resource.

GET /imports?resource=ITEM_SPECS

```
{
    "count": 6,
    "results": [
        {
            "name": "General Import Items",
            "description": "Item_Speces_create",
            "resource": "ITEM_SPECS",
            "mode": "CREATE",
            "options": {
                "createDuplicates": "ERROR",
                "multiSelectDelimiter": ";",
                "useCategoryNumberFormat": "[Use Category Number Format]",
                "stripWhiteSpace": "STRIP",
                "numberingFreeTextHeader": "Numbering Free Text",
                "mapping": [
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "revisionNumber",
                        "sourceName": "revision",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "number",
                        "sourceName": "item number",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "category.name",
                        "sourceName": "item category",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "uom",
                        "sourceName": "unit of measure",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "owner",
                        "sourceName": "owner",
                        "inResponse": true
                    }
                ]
            },
            "number": 2,
            "creationDateTime": "2023-04-26T06:01:49Z",
            "creator": {
                "fullName": "Heidi Walker",
                "email": "hwalker@everyroadgps.com",
                "guid": "9RBUZOR8OFWFYH0JSIPJ"
            },
            "guid": "Q8SBG58P5WWZI1K3M4U1"
        },
        {
            "name": "General Import Items",
            "description": "Item_Speces_create",
            "resource": "ITEM_SPECS",
            "mode": "CREATE",
            "options": {
                "createDuplicates": "ERROR",
                "multiSelectDelimiter": ";",
                "useCategoryNumberFormat": "[Use Category Number Format]",
                "stripWhiteSpace": "STRIP",
                "numberingFreeTextHeader": "Numbering Free Text",
                "mapping": [
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "revisionNumber",
                        "sourceName": "revision",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "number",
                        "sourceName": "item number",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "name",
                        "sourceName": "item name",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "procurementType",
                        "sourceName": "procurement type",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "category.name",
                        "sourceName": "item category",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "uom",
                        "sourceName": "unit of measure",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "owner",
                        "sourceName": "owner",
                        "inResponse": true
                    }
                ]
            },
            "number": 3,
            "creationDateTime": "2023-04-26T06:20:03Z",
            "creator": {
                "fullName": "Heidi Walker",
                "email": "hwalker@everyroadgps.com",
                "guid": "9RBUZOR8OFWFYH0JSIPJ"
            },
            "guid": "SAUDI7AR7YY1K3M5O6WN"
        },
        {
            "name": "General Import Items",
            "description": "Item_Speces_create",
            "resource": "ITEM_SPECS",
            "mode": "CREATE",
            "options": {
                "createDuplicates": "ERROR",
                "multiSelectDelimiter": ";",
                "useCategoryNumberFormat": "[Use Category Number Format]",
                "stripWhiteSpace": "STRIP",
                "numberingFreeTextHeader": "Numbering Free Text",
                "mapping": [
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "revisionNumber",
                        "sourceName": "revision",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "number",
                        "sourceName": "item number",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "name",
                        "sourceName": "item name",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "procurementType",
                        "sourceName": "procurement type",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "category.name",
                        "sourceName": "item category",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "uom",
                        "sourceName": "unit of measure",
                        "inResponse": true
                    },
                    {
                        "resource": "ITEM_SPECS",
                        "apiName": "owner",
                        "sourceName": "owner",
                        "inResponse": true
                    }
                ]
            },
            "number": 4,
            "creationDateTime": "2023-04-26T06:51:55Z",
            "creator": {
                "fullName": "Heidi Walker",
                "email": "hwalker@everyroadgps.com",
                "guid": "9RBUZOR8OFWFYH0JSIPJ"
            },
            "guid": "WEYHMBEVB225O7Q9SA09"
        },
        ...
    ]
}
```
Get import definitions use REPLACE mode.

GET &lt;url&gt;/imports?mode=REPLACE

```
{
    "count": 1,
    "results": [
        {
            "name": "Item_BOM_Replace",
            "description": "Item_BOM_Replace",
            "resource": "ITEM_BOM",
            "mode": "REPLACE",
            "options": {
                "matchDuplicateParents": "ERROR",
                "removeValue": "[Remove Value]",
                "multiSelectDelimiter": ";",
                "checkRefDes": "CHECK",
                "stripWhiteSpace": "STRIP"
            },
            "number": 9,
            "creationDateTime": "2023-05-03T18:53:29Z",
            "creator": {
                "fullName": "Heidi Walker",
                "email": "hwalker@everyroadgps.com",
                "guid": "9RBUZOR8OFWFYH0JSIPJ"
            },
            "guid": "9RBUZOR8OFFI1K3M5N94"
        }
    ]
}
```
Request with an invalid search attribute.

GET /imports?creator.Name=Heidi Walker

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
