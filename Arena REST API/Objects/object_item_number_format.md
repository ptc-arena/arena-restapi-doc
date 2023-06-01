# Item Number Format
In addition to all the fields from Compact Number Format, Item Number Format has a "fields" field, which is an array of the following fields:


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| creationDateTime<br> | Date-Formatted String<br> | the date and time \(in Zulu format\) a NumberFormat was created<br> |
| exampleNumber<br> | String<br> | An example of a NumberFormat<br> |
| fields<br> | Reference<br> | An array of the below fields<br> |
| apiName<br> | String<br> | The unique name of a number format field<br> |
| name<br> | String<br> | The name of a number format field<br> |
| possibleValues<br> | Array of Strings<br> | All possible values for a VALUE_LIST field. Each possible value includes value and description fields.<br> |
| type<br> | String<br> | Indicates the field type of a number format field. This value can be VALUE_LIST, DELIMITER, FREE_TEXT, AUTO_SEQUENCE<br> |
| value<br> | String<br> | The value of a number format field<br> |

