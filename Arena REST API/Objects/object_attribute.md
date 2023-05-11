# Attribute

| Field<br> | Data Type<br> | Available when<br> | Description<br> |
|  --- |  --- |  --- |  --- | 
| allowLowerCase<br> | Boolean<br> | Item Description, Item Name, Change Description, Change Title<br> | Indicates whether or not lowercase characters are allowed in values for this attribute<br> |
| allowNumbers<br> | Boolean<br> | Item Description, Item Name, Change Description, Change Title<br> | Indicates whether or not number characters are allowed in values for this attribute<br> |
| allowUpperCase<br> | Boolean<br> | Item Description, Item Name, Change Description, Change Title<br> | Indicates whether or not uppercase characters are allowed in values for this attribute<br> |
| allowNegatives<br> | Boolean<br> | fieldType is POSITIVE_DOUBLE or NUMERIC<br> | Indicates whether or not negative numbers are allowed for the attribute value. The value can be true or false.<br> |
| allowsExplicitNullValue<br> | Boolean<br> | always available<br> | Indicates whether or not submitting a value of null clears the field, resulting in no value. The value can be true or false. This value is only true for approvalDeadlineDateTime, implementationStatus, and all attributes where custom=true.<br> |
| apiName<br> | String<br> | always available<br> | For system attributes \(when custom=false\), the name of an attribute used in a request. For additional attributes \(when custom=true\), the API name is the same as the GUID.<br> |
| creatable<br> | Boolean<br> | always available<br> | Indicates whether or not an attribute value can be specified when an item is created. The value can be true or false.<br> |
| custom<br> | Boolean<br> | Item and BOM attributes<br> | Indicates whether or not an attribute is a custom attribute \(a non system\-defined attribute defined by an Account Administrator\). The value can be true or false.<br> |
| decimalPlaces<br> | Integer<br> | fieldType is POSITIVE_DOUBLE or NUMERIC<br> | The number of decimal places for a numeric value.<br> |
| defaultValue<br> | String<br> | attribute is creatable and value is not null<br> | The default value for an attribute. Only shown when its value is not null and creatable is True.<br> |
| deprecated<br> | Boolean<br> | its value is True<br> | Indicates when an attribute is being phased out of the Arena REST API.<br> |
| developerNotes<br> | String<br> | its value is not null<br> | End user information about the attribute.<br> |
| editable<br> | Boolean<br> | always available<br> | Indicates whether or not an attribute value can be specified when an item is edited. The value can be true or false.<br> |
| excludedValues<br> | Collection of Strings<br> | its value is not null<br> | Lists disallowed characters for the attribute value<br> |
| fieldType<br> | String<br> | always available<br> | The type of attribute. This value can be SINGLE_LINE_TEXT, MULTI_LINE_TEXT, BOOLEAN, DROP_DOWN, POSITIVE_DOUBLE, FIXED_DROPDOWN, NUMERIC, DATETIME<br> |
| guid<br> | String<br> | custom is True<br> | Unique identifier for the attribute.<br> |
| inViews<br> | Collection of Strings<br> | custom is False<br> | A list of views in the Arena application in which the attribute is shown.<br> |
| maxLength<br> | Number<br> | fieldType is SINGLE_LINE_TEXT, MULTI_LINE_TEXT, or DROP_DOWN<br> | The maximum length of a text field. This is used for validation.<br> |
| maxSelections<br> | Number<br> | multiSelect is True<br> | Maximum number of values allowed for the attribute.<br> |
| maxValue<br> | Double<br> | fieldType is POSITIVE_DOUBLE or NUMERIC<br> | The maximum value for an integer or double field. This is also used for validation.<br> |
| multiSelect<br> | Boolean<br> | fieldType is FIXED_DROP_DOWN<br> | Indicates whether or not an attribute can have multiple values. The value can be true or false.<br> |
| name<br> | String<br> | custom is True<br> | The name of the attribute as it appears in the Arena application.<br> |
| possibleValues<br> | Array of Strings<br> | fieldType is DROP_DOWN or FIXED_DROP_DOWN.<br> | All possible values for a drop\-down list.<br> |
| required<br> | Boolean<br> | creatable is True, global is True<br> | Indicates whether or not an attribute is Required in the workspace \(meaning a value must be supplied.\) Note that this value is true when an attribute is Required in the workspace, even when a default value exists and will be selected automatically. \(see the note below\)<br> |
| revisionControlled<br> | Boolean<br> | Item custom attributes<br> | Indicates whether or not edits to the attribute trigger the Modified flag. The value can be true or false. Only item custom attributes of type COST can be revisionControlled=false. NOTE non\-revision controlled attributes appear and can be edited on both the effective and working revisions of items whereas in the Arena application, they appear only on the effective revision.<br> |
| searchable<br> | Boolean<br> | always available<br> | Indicates whether or not an attribute can be used as a search filter. The value can be true or false.<br> |

## Note on Required/Optional Behavior and Default Values
In Arena, attributes are global \(they apply to all categories\) or category\-specific \(they apply only to spceific categories selected by Account Administrators\). Global attributes return the required property in the GET Item Attributes endpoint. Category\-specific attributes return the required property in the GET Item Category Attributes endpoint, because required/optional is defined per category.

"Required" means a value  must exist for the attribute. During creation of a new Item, the user must supply a value for required attributes with no default value. No value entry is necessary for required attributes that have a default value.

