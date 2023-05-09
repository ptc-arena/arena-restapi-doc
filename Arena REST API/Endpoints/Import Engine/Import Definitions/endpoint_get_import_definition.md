# GET Import Definition


/imports/&lt;GUID&gt;

Returns an import Definition with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
Get a specific import definition.



GET /imports/GUID

```
{
    "guid": "5N7Q4157IZGYH0HMVRLM",
    "number": 14,
    "creationDateTime": "2021-09-15T00:00:00Z",
    "creator": {
        "email": "rjohannas@everyhome.com",
        "fullName": "Roy Arena",
        "guid": "4M6P3046HYFYH0J258QJ"
    },
    "name": "CAD Import",
    "description": "Used for OnShape",
    "resource": "ITEM_SPECS",
    "mode": "OVERWRITE",
    "options": {  
        "createDuplicates": "ERROR",
        "matchDuplicates": "ERROR",
        "matchDuplicateParents": "ERROR",
        "fileEdition": "CREATE_EDITION",
        "removeValue": "[Remove Value]",
        "multiSelectDelimiter": ";",
        "useCategoryNumberFormat": "[Use Category Number Format]",
        "checkRefDes": "CHECK",
        "mapping": [  
            {
                "resource": "ITEM_SPECS",
                "apiName": "revisionNumber",
                "sourceName": "Rev"
            },
            ...
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
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
