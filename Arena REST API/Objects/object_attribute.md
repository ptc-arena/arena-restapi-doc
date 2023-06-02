# Attribute

| Field  | Data Type  | Available when  | Description  |
|  --- |  --- |  --- |  --- | 
| allowLowerCase  | Boolean  | Item Description, Item Name, Change Description, Change Title  | Indicates whether or not lowercase characters are allowed in values for this attribute  |
| allowNumbers  | Boolean  | Item Description, Item Name, Change Description, Change Title  | Indicates whether or not number characters are allowed in values for this attribute  |
| allowUpperCase  | Boolean  | Item Description, Item Name, Change Description, Change Title  | Indicates whether or not uppercase characters are allowed in values for this attribute  |
| allowNegatives  | Boolean  | fieldType is POSITIVE_DOUBLE or NUMERIC  | Indicates whether or not negative numbers are allowed for the attribute value. The value can be true or false.   |
| allowsExplicitNullValue  | Boolean  | always available  | Indicates whether or not submitting a value of null clears the field, resulting in no value. The value can be true or false. This value is only true for approvalDeadlineDateTime, implementationStatus, and all attributes where custom=true.  |
| apiName  | String  | always available  | For system attributes \(when custom=false\), the name of an attribute used in a request. For additional attributes \(when custom=true\), the API name is the same as the GUID.  |
| creatable  | Boolean  | always available  | Indicates whether or not an attribute value can be specified when an item is created. The value can be true or false.  |
| custom  | Boolean  | Item and BOM attributes  | Indicates whether or not an attribute is a custom attribute \(a non system-defined attribute defined by an Account Administrator\). The value can be true or false.  |
| decimalPlaces  | Integer  | fieldType is POSITIVE_DOUBLE or NUMERIC  | The number of decimal places for a numeric value.   |
| defaultValue  | String  | attribute is creatable and value is not null  | The default value for an attribute. Only shown when its value is not null and creatable is True.  |
| deprecated  | Boolean  | its value is True  | Indicates when an attribute is being phased out of the Arena REST API.   |
| developerNotes  | String  | its value is not null  | End user information about the attribute.   |
| editable  | Boolean  | always available  | Indicates whether or not an attribute value can be specified when an item is edited. The value can be true or false.  |
| excludedValues  | Collection of Strings  | its value is not null  | Lists disallowed characters for the attribute value  |
| fieldType  | String  | always available  | The type of attribute. This value can be SINGLE_LINE_TEXT, MULTI_LINE_TEXT, BOOLEAN, DROP_DOWN, POSITIVE_DOUBLE, FIXED_DROPDOWN, NUMERIC, DATETIME  |
| guid  | String  | custom is True  | Unique identifier for the attribute.   |
| inViews  | Collection of Strings  | custom is False  | A list of views in the Arena application in which the attribute is shown.  |
| maxLength  | Number  | fieldType is SINGLE_LINE_TEXT, MULTI_LINE_TEXT, or DROP_DOWN  | The maximum length of a text field. This is used for validation.   |
| maxSelections  | Number  | multiSelect is True  | Maximum number of values allowed for the attribute.  |
| maxValue  | Double  | fieldType is POSITIVE_DOUBLE or NUMERIC  | The maximum value for an integer or double field. This is also used for validation.   |
| multiSelect  | Boolean  | fieldType is FIXED_DROP_DOWN  | Indicates whether or not an attribute can have multiple values. The value can be true or false.  |
| name  | String  | custom is True  | The name of the attribute as it appears in the Arena application.   |
| possibleValues  | Array of Strings  | fieldType is DROP_DOWN or FIXED_DROP_DOWN.  | All possible values for a drop-down list.   |
| required  | Boolean  | creatable is True, global is True  | Indicates whether or not an attribute is Required in the workspace \(meaning a value must be supplied.\) Note that this value is true when an attribute is Required in the workspace, even when a default value exists and will be selected automatically. \(see the note below\)  |
| revisionControlled  | Boolean  | Item custom attributes  | Indicates whether or not edits to the attribute trigger the Modified flag. The value can be true or false. Only item custom attributes of type COST can be revisionControlled=false. NOTE non-revision controlled attributes appear and can be edited on both the effective and working revisions of items whereas in the Arena application, they appear only on the effective revision.   |
| searchable  | Boolean  | always available  | Indicates whether or not an attribute can be used as a search filter. The value can be true or false.  |

## Note on Required/Optional Behavior and Default Values
In Arena, attributes are global \(they apply to all categories\) or category-specific \(they apply only to spceific categories selected by Account Administrators\). Global attributes return the required property in the GET Item Attributes endpoint. Category-specific attributes return the required property in the GET Item Category Attributes endpoint, because required/optional is defined per category.

"Required" means a value  must exist for the attribute. During creation of a new Item, the user must supply a value for required attributes with no default value. No value entry is necessary for required attributes that have a default value.

