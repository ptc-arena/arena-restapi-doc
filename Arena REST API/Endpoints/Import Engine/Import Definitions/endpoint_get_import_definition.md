# GET Import Definition
/imports/&lt;GUID&gt;

Returns an import Definition with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

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
