# Quality Process Template

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| active  | Boolean  | Indicates whether or not a template is available for users to select when creating a quality process. The value can be true or false.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a template was created  |
| creator  | Reference  | The creator of a template. Contains the attribute fullName.  |
| defaultNumberFormat  | Reference  | Details of the number format used by default for processes created using a template. See Item Number Format object.  |
| defaultOwner  | Reference  | The owner that is assigned by default to processes created based upon a template  |
| description  | String  | The description of a template  |
| guid  | String  | The unique identifier for an object  |
| name  | String  | The name of an item  |
| numberFormats  | Reference  | Details of the number formats available for processes created using a template. See Quality Process Number Format object.  |
| shortName  | String  | The short name for a template  |
| steps  | Array of references  | A collection of references to steps included in a quality process template.   |

