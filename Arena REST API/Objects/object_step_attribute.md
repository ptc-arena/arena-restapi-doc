# Quality Process Step Attribute

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| active<br> | Boolean<br> | Indicates whether or not an attribute is available for Quality Process steps. The value can be true or false.<br> |
| allowNegatives<br> | Boolean<br> | Indicates whether or not a numeric value can be a negative number. The value can be true or false.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a step attribute was created.<br> |
| decimalPlaces<br> | String<br> | Indicates the number of decimal places that should be specified for the attribute.<br> |
| defaultValue<br> | String<br> | The default value for an attribute<br> |
| description<br> | String<br> | The description of an attribute<br> |
| displayAlways<br> | Boolean<br> | Indicates whether or not an attribute should always be displayed for a step, even when no value has been entered. THe value can be true or false.<br> |
| example<br> | String<br> | Example values for an attribute. Examples can help users enter acceptable values for an attribute.<br> |
| fieldType<br> | String<br> | The type of attribute. This value can be SINGLE_LINE_TEXT, MULTI_LINE_TEXT, DROP_DOWN, FIXED_DROPDOWN, DATE, or NUMBER<br> |
| guid<br> | String<br> | The unique identifier for an attribute. Step attributes always have the guid field.<br> |
| inViews<br> | String<br> | Specifies the views in which an attribute appears \(e.g. QUALITY_SUMMARY is the Summary view of a Quality Process\). This field is used only for Quality Processes.<br> |
| maskingValue<br> | String<br> | If an attribute cannot be displayed to a user \(most likely because the user's access privileges do not allow them to view it\), the masking value determines what is displayed instead. maskingValue is a system field and cannot be updated.<br> |
| name<br> | String<br> | The name of the attribute<br> |
| objectType<br> | String<br> | The type of object<br> |
| required<br> | Boolean<br> | Indicates whether the attribute is required on creation.<br> |
| possibleValues<br> | Array of Strings<br> | All possible values for a drop\-down list. This field is used only for attributes of type drop\-down list.<br> |
| userViewable<br> | Boolean<br> | Indicates whether an attribute is visible in the user interface. The value can be true or false.<br> |

