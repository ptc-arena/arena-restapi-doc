# About Export Results and the JSON Format
Export definitions with the format option set to json results in export results in the JSON file format. Certain export definitions with a specific combination of export options will result in an empty JSON export file.  

In addition to the examples below, API results include an attribute named status for the GET Item endpoint. For status, values of 0 corresponded to WORKING, values of  1 corresponded to EFFECTIVE, and values of 2 corresponded to SUPERSEDED. Later on the attribute revisionStatus was introduced with the possible values of WORKING, EFFECTIVE, and SUPERSEDED.  Status is now deprecated. Status is not included in API Exports with a JSON format.

## Empty JSON Export File Examples
* If BOM is the only export view included and BOM levels are set to none, the JSON export file will be empty since bomLevels set to none prevents any child Items from being included.

```
   "options":{
       "exportViews": [
           "BOM"
       ],
       "bomLevels":"NONE",
       "revisionStatus":"WORKING",
       "format":"json"
   }
```
* In order to export BOM substitutes, it's required to include the BOM export view. If BOM_SUBSTITUTES is included without BOM, then the JSON export file will be empty.

```
   "options":{
       "exportViews": [
           "BOM_SUBSTITUTES"
       ],
       "bomLevels":"FULL",
       "revisionStatus":"WORKING",
       "format":"json"
   }
```
* If FILES is included as an export view, but file content for Items and Supplier Items are set to NONE, the JSON export results file will be empty.

```
   "options":{
       "exportViews": [
           "FILES"
       ],
       "fileContent": {
           "item": "NONE",
           "supplierItem": "NONE"
       }
       "bomLevels":"FULL",
       "revisionStatus":"WORKING",
       "format":"json"
   }
```
* If SOURCING_SUPPLIERITEM_FILES is included as an export view, but file content is set to NONE, the JSON export results file will be empty.

```
   "options":{
       "exportViews": [
           "SOURCING_SUPPLIERITEM_FILES"
       ],
       "fileContent": {
           "item": "NONE",
           "supplierItem": "NONE"
       }
       "bomLevels":"FULL",
       "revisionStatus":"WORKING",
       "format":"json"
   }
```
