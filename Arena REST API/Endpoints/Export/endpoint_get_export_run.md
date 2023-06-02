# GET Export Run
/exports/&lt;GUID&gt;/runs/&lt;GUID&gt;

Returns an Export Run with a given GUID. 

For security reasons, only the user who ran the specific  export \(via the POST Export run\), can use this endpoint to obtain information about this specific export. Users who attempt to access the unique and specific export will encounter an error.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
Get an export definition.

GET /exports/GUID

```
{  
   "creationDateTime":"2020-03-02T12:05:06Z",  
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P3046HYFYH0J258QJ"    
   },
   "criteria":[[
      {
         "attribute":"number",
         "operator":"IS_EQUAL_TO",
         "value":"20-0001"
      }
   ]],
   "description":"Sample Potential Export with single Criterion description",
   "guid":"HZJ2GDHJUBRATCQ5TNJX",
   "name":"Sample Potential Export with single Criterion",
   "number":12,
   "options":{
     "bomLevels":"FULL",
     "exportViews":[
       "SPECS",
       "BOM",
       "FILES",
       "SOURCING",
       "FILES",
       "FILES_FILE_SUMMARY",
       "SOURCING_SUPPLIERITEM_SPECS",
       "SOURCING_SUPPLIERITEM_SPECS_PROFILE",
       "SOURCING_SUPPLIERITEM_FILES",
       "SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY",
     ],
     "fileContent":{
        "item":"PRIMARY",
        "supplierItem":"ALL"
     },
     "header":"name"
     "revisionStatus":"POTENTIAL",
     "format":"csv"
   },
   "world":"ITEMS"
}
```
request made by a user who did not initiate the export run.

```
{  
   "status":403,
   "errors":[  
      {  
         "code":3024,
         "message":"Either you do not have privileges to access the requested data or it does not exist."
      }
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
