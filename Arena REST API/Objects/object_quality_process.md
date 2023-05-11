# Quality Process

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| completedDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a Quality Process was completed<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a Quality Process was created<br> |
| creator<br> | Reference<br> | The user who created the Quality Process. Contains the atrributes fullName and guid.<br> |
| currentStep<br> | Reference<br> | Details of the current step of the Quality Process. This listing includes the attributes approvals \(null unless sign\-off step\), attributes, and guid.<br> |
| description<br> | String<br> | The description of a template<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| name<br> | String<br> | The name of a Quality Process<br> |
| number<br> | String<br> | The number of a Quality Process<br> |
| owner<br> | Reference<br> | The name of the user who owns the Quality Process. Contains the attributes fullName and guid.<br> |
| status<br> | Boolean<br> | The status of a Quality Process. Value can be OPEN or COMPLETE.<br> |
| statusMode<br> | Boolean<br> | The mode by which the status attribute advances from OPEN to COMPLETE. Value can be AUTOMATIC or MANUAL. Default value is MANUAL.<br> |
| targetCompletionDate<br> | Date\-Formatted String<br> | The date a Quality Process is targeted for completion<br> |
| template<br> | Reference<br> | Details of the template upon which a process was based. Contains the attributes active and guid.<br> |
| type<br> | String<br> | The type of the Quality Process. NOTE this always returns null.<br> |

