# GET Import Run


/imports/&lt;GUID&gt;/runs/&lt;GUID&gt;

Returns an Import Run with a given GUID. 

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
Get a specific prrevious import engine  run.



GET /imports/&lt;GUID&gt;/runs/&lt;GUID&gt;

```
{
    "guid": "R9TCQNRT4L47Q9VQWUF3",
    "number": 14,
    "creationDateTime": "2021-09-15T00:00:00Z",
    "creator": {
        "email": "rjones@arenasolutions.com",
        "fullName": "Roy Arena",
        "guid": "4M6P3046HYFYH0J258QJ"
    },
    "submitFileType": "EXCEL_WORKSHEET",
    "submitWorksheetName": "Item Master",
    "completionDateTime": "2021-09-16T00:00:00Z",
    "status": "COMPLETE",
    "warnings": {
        "count": 12,
        "results": [
            {
                "code": 331,
                "message": "Column 'Descrptn' ignored."
            },
            ...
        ]
    },
    "commit": false,
    "totalCount": 134881,
    "successCount": 134862,
    "errorCount": 19,
    "options": {    
        "timeZone": "???",
        "addToChange": {
            "number": "ECO-002114"
        }
    },
    "changes": [
        { 
            "category": {
                "guid": "L3N6KHLNYFY8RAQ8SWYT",
                "name": "Engineering Change Order",
                "path": "Change\\Change Order\\Engineering Change Order"
            },
            "creationDateTime": "2021-09-14T23:58:41Z",
            "creator": {
                "email": "integration@customer.com",
                "fullName": "Mr. Integration",
                "guid": "J1L4IFJLWDUDWFYHPRYT"
            },
            "effectiveDateTime": null,
            "guid": "J1L4IFJLWDWZI0GL6I34",
            "lifecycleDateTime": "2021-09-14T23:58:41Z",
            "lifecycleStatus": {
                "type": "OPEN_AND_UNLOCKED"
            },
            "number": "ECO-002114",
            "submissionDateTime": null,
            "title": "From an integration!"
        },
        ...
    ]
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
