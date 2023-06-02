# Quality Process Step

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| allowOwnerToAddApprovers  | Boolean  | Determines if a step owner can add users to the step as approvers. Available only for steps of type SIGNOFF.   |
| approvals  | Array of References  | A reference to the approvals entered by approver users. Each value contains the attributes fullName and guid. Available only for steps of type SIGNOFF.   |
| assignee\*  | String  | **DEPRECATED - Please use assignees** The user to whom a step is assigned. Contains the attribute fullName. Deprecated as of Winter 2021 release.  |
| assignees  | Array of References  | A reference to the assignee of a Quality step. Lists users if assignee is a single user. Lists userGroups if assignee is a User Group.  |
| attributes  | Array of References  | A reference to the attributes on a step. Each value contains the attributes apiName, fieldType, guid, name, and value. Available only for steps of type REGULAR.  |
| completeDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a step was completed  |
| completeUser  | String  | The user who completed the step. Contains the attribute fullName.  |
| dueDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) the step must be completed NOTE: Only the date portion of this string is honored. Time always appears as 23:59:59 local time.  |
| guid  | String  | The unique identifier for an object  |
| name  | String  | The name of a step  |
| order  | Integer  | The numeric value that determines a step's position in a process  |
| status  | Boolean  | The status of a Quality Process. Value can be OPEN or COMPLETE  |
| type  | Boolean  | Determines if a step includes approvals or not. Values are REGULAR and SIGNOFF. Default value is REGULAR.  |
| users  | String  | The user assigned to the Quality step. Also used to list the members of a User Group.  |
| userGroups  | String  | The User Group assigned to the quality step. Followed by an array of users that comprise the User Group.  |

