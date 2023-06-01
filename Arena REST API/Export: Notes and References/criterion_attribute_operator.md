# Criteria: Attributes and Operators
Item Attributes that can be used in criteria.

## Supported Criteria Attributes and Their Supported Operators

| Attribute<br> | Field Type<br> | Operators<br> |
|  --- |  --- |  --- | 
| number<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| guid<br> | GUID<br> | IS_EQUAL_TO, IS_IN<br> |
| effectiveDateTime<br> | DATETIME<br> | IS_BEFORE, IS_AFTER, IS_BETWEEN<br> |
| revisionNumber<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| description<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| category.guid\*<br> | GUID<br> | IS_EQUAL_TO, IS_IN<br> |
| category.name<br> | FIXED_DROP_DOWN \(Single Select\)<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| owner.fullName<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| creator.guid<br> | GUID<br> | IS_EQUAL_TO<br> |
| creator.fullName<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| creator.email<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| lifecyclePhase.guid<br> | GUID<br> | IS_EQUAL_TO, IS_IN<br> |
| lifecyclePhase.name<br> | FIXED_DROP_DOWN \(Single Select\)<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO<br> |
| lifecyclePhase.stage<br> | FIXED_DROP_DOWN \(Single Select\)<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO<br> |
| creationDateTime<br> | DATETIME<br> | IS_EQUAL_TO, IS_BEFORE, IS_AFTER, IS_BETWEEN<br> |
| modifiedBOM\*<br> | BOOLEAN<br> | IS_EQUAL_TO<br> |
| modifiedSpecs\*<br> | BOOLEAN<br> | IS_EQUAL_TO<br> |
| modifiedSourcing\*<br> | BOOLEAN<br> | IS_EQUAL_TO<br> |
| modifiedFiles\*<br> | BOOLEAN<br> | IS_EQUAL_TO<br> |
| any<br> | SINGLE_LINE_TEXT<br> | CONTAINS<br> |
| supplier.name<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| supplier.guid<br> | GUID<br> | IS_EQUAL_TO<br> |
| supplierItem.name<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
| supplierItem.guid<br> | GUID<br> | IS_EQUAL_TO<br> |
| Additional Attributes \(Various Types\)<br> | SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
|   | MULTI_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> |
|   | FIXED_DROP_DOWN<br> | IS_IN, IS_NOT_IN<br> |
|   | FIXED_DROP_DOWN \(Pre-defined, Single Select\)<br> | IS_IN, IS_NOT_IN<br> |
|   | FIXED_DROP_DOWN \(Pre-defined, Multi-Select\)<br> | IS_IN, IS_NOT_IN<br> |
|   | DATETIME<br> | IS_EQUAL_TO, IS_BEFORE, IS_AFTER, IS_BETWEEN<br> |
|   | NUMBER<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THAN, IS_GREATOR_THAN_OR_EQUAL_TO, IS_GREATOR_THAN<br> |

Table of Criterion Operators organized by field type.


| fieldType<br> | Operators<br> | Data Type<br> |
|  --- |  --- |  --- | 
| SINGLE_LINE_TEXT<br> | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> | String<br> |
| GUID<br> | IS_IN<br> | Array of Strings<br> |
| DATETIME<br> | IS_EQUAL_TO, IS_BEFORE, IS_AFTER<br> | String \(Date\)<br> |
| DATETIME<br> | IS_BETWEEN<br> | Array of 2 Strings \(Date\). Dates must be in chronological order.<br> |
| BOOLEAN<br> | IS_EQUAL_TO<br> | Boolean<br> |
| DATE<br> | IS_BEFORE, IS_AFTER<br> | String \(Date\)<br> |
| DATE<br> | IS_BETWEEN<br> | Array of 2 Strings \(Date\). Dates must be in chronological order.<br> |
| DROP_DOWN<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO<br> | Array of Strings<br> |
| FIXED_DROP_DOWN, multi-select<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO<br> | Array of Strings<br> |
| FIXED_DROP_DOWN, single select<br> | IS_EQUAL_TO, IS_NOT_EQUAL_TO<br> | Array of Strings<br> |
| MULTI_LINE_TEXT<br> | IS_EQUAL_TO, IS_LESS_THAN_OR EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH<br> | String<br> |
| NUMBER<br> | IS_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THANK, IS_GREATER_THAN_OR_EQUAL_TO, IS_GREATER_THAN<br> | Number<br> |
| POSITIVE_DOUBLE<br> | IS_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THAN, IS_GREATER_THAN_OR_EQUAL_TO<br> | Number<br> |


            
            
            
            
            
            
            
          

* Searches for "SINGLE_LINE_TEXT": "IS_EQUAL_TO" and "IS_NOT_EQUAL_TO" user astrisk literally and not as a wildcard.

* Searches for "SINGLE_LINE_TEXT": "CONTAINS", "DOES_NOT_CONTAIN", "STARTS_WITH", "DOES_NOT_START_WITH" use astrisk as a wild card.

* All other fieldTypes do not support the use of asterisk as wild cards.

* Searching field types DROP_DOWN and FIXED_DROPDOWN (both single and multiple select) permit submission of multiple values. The multiple values are separated by a semi-colon.

* If fieldType GUID is included in the criteria, only one criterion is supported. In other words, if GUID is included, no other criterion or criterion groups are permitted.

* Arena Export currently doesn't support export for category.guid using the GUID for uncategorized. The category.guid works for all other categorized GUIDs. To run an export for uncategorized Items use the following criteria: attribute is euqal to category.name, operator is IS_EQUAL_TO, and value is -uncategorized-.

* For an Item Export with revisionStatus set to LATEST used in conjunction with modfieidBOM equals true or modifiedBOM equals false, the modifiedBOM attribute refers to the working revision for  those released Items. The reason for this is because released, effective revisions can't have a modified BOM. Only working revision Items can have a modified BOM. In other words, if you run an export for modifiedBOM equals true and revisionStatus equals LATEST and you're results show released Items with modifiedBOM set to false then it is an indicator that the modifiedBOM is in the working revision of that Item. This behavior extends to exports that use modifiedSpecs, modifiedSourcing, and modifiedFiles used in conjunction with revisionStatus set to LATEST.

