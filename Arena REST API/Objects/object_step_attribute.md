# Quality Process Step Attribute

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| active | Boolean | Indicates whether or not an attribute is available for Quality Process steps. The value can be true or false. |
| allowNegatives | Boolean | Indicates whether or not a numeric value can be a negative number. The value can be true or false. |
| creationDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a step attribute was created. |
| decimalPlaces | String | Indicates the number of decimal places that should be specified for the attribute.  |
| defaultValue | String | The default value for an attribute |
| description | String | The description of an attribute |
| displayAlways | Boolean | Indicates whether or not an attribute should always be displayed for a step, even when no value has been entered. THe value can be true or false. |
| example | String | Example values for an attribute. Examples can help users enter acceptable values for an attribute. |
| fieldType | String | The type of attribute. This value can be SINGLE_LINE_TEXT, MULTI_LINE_TEXT, DROP_DOWN, FIXED_DROPDOWN, DATE, or NUMBER |
| guid | String | The unique identifier for an attribute. Step attributes always have the guid field. |
| inViews | String | Specifies the views in which an attribute appears \(e.g. QUALITY_SUMMARY is the Summary view of a Quality Process\). This field is used only for Quality Processes. |
| maskingValue | String | If an attribute cannot be displayed to a user \(most likely because the user's access privileges do not allow them to view it\), the masking value determines what is displayed instead. maskingValue is a system field and cannot be updated. |
| name | String | The name of the attribute |
| objectType | String | The type of object |
| required | Boolean | Indicates whether the attribute is required on creation.  |
| possibleValues | Array of Strings | All possible values for a drop\-down list. This field is used only for attributes of type drop\-down list. |
| userViewable | Boolean | Indicates whether an attribute is visible in the user interface. The value can be true or false. |

