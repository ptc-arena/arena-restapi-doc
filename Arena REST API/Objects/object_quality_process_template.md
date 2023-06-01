# Quality Process Template

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| active<br> | Boolean<br> | Indicates whether or not a template is available for users to select when creating a quality process. The value can be true or false.<br> |
| creationDateTime<br> | Date-Formatted String<br> | the date and time \(in Zulu format\) a template was created<br> |
| creator<br> | Reference<br> | The creator of a template. Contains the attribute fullName.<br> |
| defaultNumberFormat<br> | Reference<br> | Details of the number format used by default for processes created using a template. See object.<br>Item Number Format<br> |
| defaultOwner<br> | Reference<br> | The owner that is assigned by default to processes created based upon a template<br> |
| description<br> | String<br> | The description of a template<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| name<br> | String<br> | The name of an item<br> |
| numberFormats<br> | Reference<br> | Details of the number formats available for processes created using a template. See object.<br>Quality Process Number Format<br> |
| shortName<br> | String<br> | The short name for a template<br> |
| steps<br> | Array of references<br> | A collection of references to steps included in a quality process template.<br> |

