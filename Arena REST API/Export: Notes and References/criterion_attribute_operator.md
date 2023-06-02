# Criteria: Attributes and Operators
Item Attributes that can be used in criteria.

## Supported Criteria Attributes and Their Supported Operators

| Attribute  | Field Type  | Operators  |
|  --- |  --- |  --- | 
| number  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| guid  | GUID  | IS_EQUAL_TO, IS_IN  |
| effectiveDateTime  | DATETIME  | IS_BEFORE, IS_AFTER, IS_BETWEEN  |
| revisionNumber  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| description  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| category.guid\*  | GUID  | IS_EQUAL_TO, IS_IN  |
| category.name  | FIXED_DROP_DOWN \(Single Select\)  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| owner.fullName  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| creator.guid  | GUID  | IS_EQUAL_TO  |
| creator.fullName  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| creator.email  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| lifecyclePhase.guid  | GUID  | IS_EQUAL_TO, IS_IN  |
| lifecyclePhase.name  | FIXED_DROP_DOWN \(Single Select\)  | IS_EQUAL_TO, IS_NOT_EQUAL_TO  |
| lifecyclePhase.stage  | FIXED_DROP_DOWN \(Single Select\)  | IS_EQUAL_TO, IS_NOT_EQUAL_TO  |
| creationDateTime  | DATETIME  | IS_EQUAL_TO, IS_BEFORE, IS_AFTER, IS_BETWEEN  |
| modifiedBOM\*  | BOOLEAN  | IS_EQUAL_TO  |
| modifiedSpecs\*  | BOOLEAN  | IS_EQUAL_TO  |
| modifiedSourcing\*  | BOOLEAN  | IS_EQUAL_TO  |
| modifiedFiles\*  | BOOLEAN  | IS_EQUAL_TO  |
| any  | SINGLE_LINE_TEXT  | CONTAINS  |
| supplier.name  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| supplier.guid  | GUID  | IS_EQUAL_TO  |
| supplierItem.name  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
| supplierItem.guid  | GUID  | IS_EQUAL_TO  |
| Additional Attributes \(Various Types\)  | SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
|   | MULTI_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  |
|   | FIXED_DROP_DOWN  | IS_IN, IS_NOT_IN  |
|   | FIXED_DROP_DOWN \(Pre-defined, Single Select\)  | IS_IN, IS_NOT_IN  |
|   | FIXED_DROP_DOWN \(Pre-defined, Multi-Select\)  | IS_IN, IS_NOT_IN  |
|   | DATETIME  | IS_EQUAL_TO, IS_BEFORE, IS_AFTER, IS_BETWEEN  |
|   | NUMBER  | IS_EQUAL_TO, IS_NOT_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THAN, IS_GREATOR_THAN_OR_EQUAL_TO, IS_GREATOR_THAN  |

Table of Criterion Operators organized by field type.


| fieldType  | Operators  | Data Type  |
|  --- |  --- |  --- | 
| SINGLE_LINE_TEXT  | IS_EQUAL TO, IS_NOT_EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  | String  |
| GUID  | IS_IN  | Array of Strings  |
| DATETIME  | IS_EQUAL_TO, IS_BEFORE, IS_AFTER  | String \(Date\)  |
| DATETIME  | IS_BETWEEN  | Array of 2 Strings \(Date\). Dates must be in chronological order.  |
| BOOLEAN  | IS_EQUAL_TO  | Boolean  |
| DATE  | IS_BEFORE, IS_AFTER  | String \(Date\)  |
| DATE  | IS_BETWEEN  | Array of 2 Strings \(Date\). Dates must be in chronological order.  |
| DROP_DOWN  | IS_EQUAL_TO, IS_NOT_EQUAL_TO  | Array of Strings  |
| FIXED_DROP_DOWN, multi-select  | IS_EQUAL_TO, IS_NOT_EQUAL_TO  | Array of Strings  |
| FIXED_DROP_DOWN, single select  | IS_EQUAL_TO, IS_NOT_EQUAL_TO  | Array of Strings  |
| MULTI_LINE_TEXT  | IS_EQUAL_TO, IS_LESS_THAN_OR EQUAL_TO, CONTAINS, DOES_NOT_CONTAIN, STARTS_WITH, DOES_NOT_START_WITH  | String  |
| NUMBER  | IS_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THANK, IS_GREATER_THAN_OR_EQUAL_TO, IS_GREATER_THAN  | Number  |
| POSITIVE_DOUBLE  | IS_EQUAL_TO, IS_LESS_THAN_OR_EQUAL_TO, IS_LESS_THAN, IS_GREATER_THAN_OR_EQUAL_TO  | Number  |



* Searches for "SINGLE_LINE_TEXT": "IS_EQUAL_TO" and "IS_NOT_EQUAL_TO" user astrisk literally and not as a wildcard.

* Searches for "SINGLE_LINE_TEXT": "CONTAINS", "DOES_NOT_CONTAIN", "STARTS_WITH", "DOES_NOT_START_WITH" use astrisk as a wild card.

* All other fieldTypes do not support the use of asterisk as wild cards.

* Searching field types DROP_DOWN and FIXED_DROPDOWN (both single and multiple select) permit submission of multiple values. The multiple values are separated by a semi-colon.

* If fieldType GUID is included in the criteria, only one criterion is supported. In other words, if GUID is included, no other criterion or criterion groups are permitted.

* Arena Export currently doesn't support export for category.guid using the GUID for uncategorized. The category.guid works for all other categorized GUIDs. To run an export for uncategorized Items use the following criteria: attribute is euqal to category.name, operator is IS_EQUAL_TO, and value is -uncategorized-.

* For an Item Export with revisionStatus set to LATEST used in conjunction with modfieidBOM equals true or modifiedBOM equals false, the modifiedBOM attribute refers to the working revision for  those released Items. The reason for this is because released, effective revisions can't have a modified BOM. Only working revision Items can have a modified BOM. In other words, if you run an export for modifiedBOM equals true and revisionStatus equals LATEST and you're results show released Items with modifiedBOM set to false then it is an indicator that the modifiedBOM is in the working revision of that Item. This behavior extends to exports that use modifiedSpecs, modifiedSourcing, and modifiedFiles used in conjunction with revisionStatus set to LATEST.

