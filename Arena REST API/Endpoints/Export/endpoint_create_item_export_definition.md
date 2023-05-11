# POST Export Definition


/exports

Creates a new  Export Definition object.  Each case is shown below.

NOTES:

* Export Definitions cannot be edited or deleted.

* Criteria can be specified in the Export Definition or in the Export Run. 

* Criteria cannot be specified in both the Export Definition and in the Export Run. It also cannot be specified in neither.

* Export results are saved in Arena and expire after 60 days. Once expired, the results files are deleted in Arena and are no longer available.

* Export Limits: If the criteria return more than 20,000 items, then an error shall be returned. If the criteria return more than 5,000 item, and BOM and FILES view are included as exportViews, then an error shall be returned.

* For an Item Export with revisionStatus set to LATEST used in conjunction with modifiedBOM equals true or modifiedBOM equals false, the modifiedBOM attribute refers to the working revision for  those released Items. The reason for this is because released, effective revisions can't have a modified BOM. Only working revision Items can have a modified BOM. In other words, if you run an export for modifiedBOM equals true and revisionStatus equals LATEST and you're results show released Items with modifiedBOM set to false then it is an indicator that the modifiedBOM is in the working revision of that Item. This behavior extends to exports that use modifiedSpecs, modifiedSourcing, and modifiedFiles used in conjunction with revisionStatus set to LATEST.

* Arena Export currently doesn't support export for category.guid using the GUID for uncategorized. The category.guid works for all other categorized GUIDs. To run an export for uncategorized Items use the following criteria: attribute is euqal to category.name, operator is IS_EQUAL_TO, and value is \-uncategorized\-.

* An Item Export with revisionStatus set to WORKING or POTENTIAL, will return the working revision of the Items even if these Items contain an efffective, released version.

* A full list of Export Options can be found in .

* If an export has a JSON format and certain Export Options selected it can result in a JSON export file without any content. See .

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
* Create Export Definition with no Criteria

```
{  
   "name":"Sample Potential Export",
   "description":"Sample Potential Export Description",
   "world":"ITEMS",
   "options":{
     "exportViews":[
       "SPECS",
       "BOM",
       "SOURCING",
       "FILES",
       "FILES_FILE_SUMMARY",
       "SOURCING_SUPPLIERITEM_SPECS",
       "SOURCING_SUPPLIERITEM_SPECS_PROFILE",
       "SOURCING_SUPPLIERITEM_FILES",
       "SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY"
     ],
     "bomLevels":"FULL",
     "fileContent":{
        "item":"PRIMARY",
        "supplierItem":"ALL"
     },
     "header": "apiName",
     "revisionStatus": "Working",
     "format": "json"
   },
   "criteria":null,
}
```
* Create Export Definition with a single Criterion

```
{  
   "name":"Sample Potential Export with single Criterion",
   "description":"Sample Potential Export with single Criterion description",
   "world":"ITEMS",
   "options":{
     "exportViews":[
       "SPECS",
       "BOM",
       "SOURCING",
       "FILES",
       "FILES_FILE_SUMMARY",
       "SOURCING_SUPPLIERITEM_SPECS",
       "SOURCING_SUPPLIERITEM_SPECS_PROFILE",
       "SOURCING_SUPPLIERITEM_FILES",
       "SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY"
     ],
     "bomLevels": "FULL",
     "fileContent":{
        "item":"PRIMARY",
        "supplierItem":"ALL"
     }
     "header":"name",
     "revisionStatus": "POTENTIAL",
     "format": "csv"
   },
   "criteria":[[
      {
         "attribute": "number",
         "operator": "IS_EQUAL_TO",
         "value": "20-0001"
      }
   ]]
}
```
* Create Export Definition with two Criterion separated with criterion logic

```
{  
   "name":"Sample Effective Export with two criterion separated with criterion logic",
   "description":"Sample Effective Export with two criterion separated with criterion logic Description",
   "world":"ITEMS",
   "options":{
     "exportViews":[
       "SPECS",
       "BOM",
       "SOURCING",
       "FILES",
       "FILES_FILE_SUMMARY",
       "SOURCING_SUPPLIERITEM_SPECS",
       "SOURCING_SUPPLIERITEM_SPECS_PROFILE",
       "SOURCING_SUPPLIERITEM_FILES",
       "SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY"
     ],
     "bomLevels":"FULL",
     "fileContent":{
        "item":"PRIMARY",
        "supplierItem":"ALL"
     }
     "header":"name"
     "revisionStatus":"LATEST",
     "format": "json"
   },
   "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"20-"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_AFTER",
           "value":"2016-01-02T12:01:07Z"
         }
      ]]
}
```
* Create Export Definition with two Criterion groups separated by criterion group logic.

```
{  
   "name":"An example of an export definition with two Criterion groups",
   "description":"Description of an export definition with two criterion groups",
   "world":"ITEMS",
   "options":{
     "exportViews":[
       "SPECS",
       "BOM",
       "SOURCING",
       "FILES",
       "FILES_FILE_SUMMARY",
       "SOURCING_SUPPLIERITEM_SPECS",
       "SOURCING_SUPPLIERITEM_SPECS_PROFILE",
       "SOURCING_SUPPLIERITEM_FILES",
       "SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY"
     ],
     "bomLevels":"FULL",
     "fileContent":{
        "item":"PRIMARY",
        "supplierItem":"ALL"
     }
     "header":"name",
     "revisionStatus":"LATEST",
     "format": "json"
   },
   "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"20-"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_AFTER",
           "value":"2015-05-02T12:00:00Z"
         }
      ],
      "OR",
     [  
        {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"2"
        },
        "AND",
        {
           "attribute":"effectiveDateTime",
           "operator":"IS_BEFORE",
           "value":"2019-11-02T12:00:00Z"
        }
     ]
   ]
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Create Export Definition with no Criteria

```
{  
   "creationDateTime":"2020-03-01T14:32:25Z",  
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P3046HYFYH0J258QJ"    
   },
   "criteria":null,
   "description":"Sample Potential Export Description",
   "guid":"HZJ2GDHJUBRATCQ5TNJX",
   "name":"Sample Potential Export Description",
   "number":12,
   "options":{
     "bomLevels":"FULL",
     "exportViews":[
       "SPECS",
       "BOM",
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
     "header":"apiName",
     "revisionStatus":"POTENTIAL",
     "format": "json"
   },
   "world":"ITEMS"
}
```
Create Export Definition with a single criterion

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
     "header":"apiName",
     "revisionStatus":"POTENTIAL",
     "format": "csv"
   },
   "world":"ITEMS"
}
```
Create Export Definition with two Criterion separated with criterion logic

```
{  
   "creationDateTime":"2020-03-04T16:30:25Z",  
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P3046HYFYH0J258QJ"    
   },
   "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"20-"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_EQUAL_TO",
           "value":"2018-03-16T12:00:00Z"
         }
      ]
},
   "description":"Sample Effective Export with two criterion separated with criterion logic Description",
   "guid":"HZJ2GDHJUBRATCQ5TNJX",
   "name":"Sample Effective Export with two criterion separated with criterion logic Description",
   "number":12,
   "options":{
     "bomLevels":"FULL",
     "exportViews":[
       "SPECS",
       "BOM",
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
     "header":"apiName",
     "revisionStatus":"LATEST",
     "format":"json"
   },
   "world":"ITEMS"
}
```
Create Export Definition with two Criterion groups separated by criterion gorup logic

```
{   
   "creationDateTime":"2020-03-05T10:30:35Z",  
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P3046HYFYH0J258QJ"    
   },
"criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"20-"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_EQUAL_TO",
           "value":"2018-02-24T12:00:00Z"
         }
      ],
      "OR",
     [  
        {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"5"
        },
        "AND",
        {
           "attribute":"effectiveDateTime",
           "operator":"IS_EQUAL_TO"
           "value":"2015-05-02T12:00:00Z"
        }
     ]
},
   "description":"Sample Effective Export with two criterion separated with criterion logic Description",
   "guid":"HZJ2GDHJUBRATCQ5TNJX",
   "name":"Sample Effective Export with two criterion separated with criterion logic Description",
   "number":12,
   "options":{
     "bomLevels":"FULL",
     "exportViews":[
       "SPECS",
       "BOM",
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
     "header":"apiName",
     "revisionStatus":"LATEST",
     "format": "json"
   },
   "world":"ITEMS"
}
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

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
