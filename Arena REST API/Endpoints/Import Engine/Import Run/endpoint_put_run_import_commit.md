# PUT Import Commit
/imports/&lt;GUID&gt;/runs/&lt;GUID&gt;

When performing a POST import run endpoint, users can set the commit value to false. The import then can use information within the response and GET import run error content or GET import run results content to find any errors within an import run. This allows users to double check for any import errors without commiting it to the workspace.

Once the user has completed troubleshooting the errors, they can then use this PUT Import commit endpoint to commit the import to the workspace.

Please note that this endpoint is uni-directional. Once the import commit has been set to true, it cannot be returned to a value of false.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
* Commit and "finish" an import run. Once set to true, the import run commit attribute cannot be set back to false.

```
{
    "commit": true
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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
Import Run has successfully been commited to the workspace.

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
         "commit": true,
         "totalCount": 134881,
         "successCount": 134862,
         "errorCount": 19,
         "options": {    
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
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

* A value in the import definition is invalid.

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
