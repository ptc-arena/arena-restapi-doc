# Quality Process Template Step

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| guid<br> | String<br> | The unique identifier for an object<br> |
| name<br> | String<br> | The name of a step<br> |
| order<br> | Integer<br> | The numeric value that determines a step's position in a process<br> |
| type<br> | Boolean<br> | Determines if a step includes approvers or not. Values are REGULAR and SIGNOFF. Default value is REGULAR.<br> |
| attributes<br> | Array of References<br> | A reference to the attributes on a step. Each value contains the attribute guid. Available only for steps of type REGULAR.<br> |
| allowOwnerToAddApprovers<br> | Boolean<br> | Determines if a step owner can add users to the step as approvers. Available only for steps of type SIGNOFF.<br> |
| approvers<br> | Array of References<br> | A reference to the approvers included in a step. Each value contains the attribute fullName. Available only for steps of type SIGNOFF.<br> |

