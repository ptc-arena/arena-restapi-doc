# GET Import Definitions (Search)
/imports?query_string

Returns a collection of Import Definition objects matching the given search criteria.. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all import definitions where results should begin. All import definitions before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| name  | string  | A user defined name for the import definition. it must be provided on creation and does not need to be unique.  |
| number  | string  | A system generated number starting at 1 and incrementing with each export.   |
| description  | string  | description of the import definition  |
| creator.guid  | GUID  | The unique identifier for the creator of the Export Definition.  |
| creator.email  | string  | The email address of the user account that created the import Definition.  |
| creator.fullName  | string  | The full name of the user that created the Import Definition.  |
| mode  | string  | The Mode of the import. The mode dictates the function of the import.  |

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
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
