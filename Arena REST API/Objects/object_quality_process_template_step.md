# Quality Process Template Step

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| guid  | String  | The unique identifier for an object  |
| name  | String  | The name of a step  |
| order  | Integer  | The numeric value that determines a step's position in a process  |
| type  | Boolean  | Determines if a step includes approvers or not. Values are REGULAR and SIGNOFF. Default value is REGULAR.  |
| attributes  | Array of References  | A reference to the attributes on a step. Each value contains the attribute guid. Available only for steps of type REGULAR.  |
| allowOwnerToAddApprovers  | Boolean  | Determines if a step owner can add users to the step as approvers. Available only for steps of type SIGNOFF.   |
| approvers  | Array of References  | A reference to the approvers included in a step. Each value contains the attribute fullName. Available only for steps of type SIGNOFF.  |

