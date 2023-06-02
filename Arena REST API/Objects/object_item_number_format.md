# Item Number Format
In addition to all the fields from Compact Number Format, Item Number Format has a "fields" field, which is an array of the following fields:


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a NumberFormat was created  |
| exampleNumber  | String  | An example of a NumberFormat  |
| fields  | Reference  | An array of the below fields  |
| apiName  | String  | The unique name of a number format field  |
| name  | String  | The name of a number format field  |
| possibleValues  | Array of Strings  | All possible values for a VALUE_LIST field. Each possible value includes value and description fields.  |
| type  | String  | Indicates the field type of a number format field. This value can be VALUE_LIST, DELIMITER, FREE_TEXT, AUTO_SEQUENCE  |
| value  | String  | The value of a number format field  |

