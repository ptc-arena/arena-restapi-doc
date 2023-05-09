# POST Item Definition


/imports

Creates a new  Import Definition object.  Note that all Import Engine endpoints are only supported in Access Policies workspaces..

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
* Import Definition for creating Items and adding them to a change. Includes custom mapping.

```
{
    "name": "Item_Specs_Create_0331",
    "description": "Item_Specs_Create_0331",
    "resource": "item_specs",
    "mode": "create",
    "options": {
        "createDuplicates": "ALLOW",
        "mapping": [
            {
                "resource": "item_specs",
                "apiName": "revisioNumber",
                "sourceName": "Revd"
            },
            {
                "resource": "item_specs",
                "apiName": "procurementType",
                "sourceName": "procurementType"
            }
            {
                "resource": "item_specs",
                "apiName": "Date Zero",
                "sourceName": "Date Zero"
            },
            {
                "resource": "import",
                "apiName": "errormessage",
                "sourceName": "error messages"
            }
        ],
        "addToChange": {
            "effectivityType": "PERMANENT_ON_APPROVAL",
            "category": {
                "guid": "L3N6KHLNYFY8RAQ8SWYT"
            },
            "numberSequencePrefix": {
                "value": "ECO-"
            },
            "title": "New CAD Release",
            "routings": [
                {
                    "guid": "7P9S6379K1IL4N6P4QFB"
                }
            ]
        }
    }
}
```
* Import Definition BOM replacement.  Uses default mapping.

```
{
    "name": "Item_BOM_Replace",
    "description": "Item_BOM_Replace",
    "resource": "ITEM_BOM",
    "mode": "Replace",
    "options": {    
        "createDuplicates": "ERROR",
        "matchDuplicates": "ERROR",
        "matchDuplicateParents": "ERROR",
        "removeValue": "[Remove Value]",
        "multiSelectDelimiter": ";",
        "useCategoryNumberFormat": "[Use Category Number Format]"
    }
}
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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
Import Definition for creating Items and adding them to a change. Includes custom mapping.

```
{
    "name": "Item_Specs_Create_0331",
    "description": "Item_Specs_Create_0331",
    "resource": "item_specs",
    "mode": "create",
    "options": {
        "createDuplicates": "ALLOW",
        "mapping": [
            {
                "resource": "item_specs",
                "apiName": "revisioNNUMBER",
                "sourceName": "Revd"
            },
            {
                "resource": "item_specs",
                "apiName": "procurementType",
                "sourceName": "procurementType"
            }
            {
                "resource": "item_specs",
                "apiName": "Date Zero",
                "sourceName": "Date Zero"
            },
            {
                "resource": "import",
                "apiName": "errormessage",
                "sourceName": "error messages"
            }
        ],
                "addToChange": {
            "effectivityType": "PERMANENT_ON_APPROVAL",
            "category": {
                "guid": "L3N6KHLNYFY8RAQ8SWYT"
            },
            "numberSequencePrefix": {
                "value": "ECO-"
            },
            "title": "New CAD Release",
            "routings": [
                {
                    "guid": "7P9S6379K1IL4N6P4QFB"
                }
            ]
        }
    "number": 9,
    "creationDateTime": "2023-05-03T18:53:29Z",
    "creator": {
        "fullName": "Heidi Walker",
        "email": "hwalker@everyroadgps.com",
        "guid": "9RBUZOR8OFWFYH0JSIPJ"
    },
    "guid": "9RBUZOR8OFFI1K3M5N94"
}

```
Import Definition BOM replacement.  Uses default mapping.

```
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
```
* A field is not creatable. 

```

{  
   "status":400,
   "errors":[  
      {  
         "code":4004,
         "message":"The attribute \"name1\" is not creatable."
      }
   ]
}
```
* A value in the export definition is invalid.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The specified value \"Changes\" is not a valid option for the attribute \"world\"."
      }
   ]
}
```
* A required field is missing.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3006,
         "message":"The attribute \"Description\" is required."
      }
   ]
}
```
* An invalid export option is used such as inputting PRIMARY for supplierItem when defining fileContent.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":4003,
         "message":"The value for the attribute \"supplierItem\" is not valid."
      }
   ]
}
```
