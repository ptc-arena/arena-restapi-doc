# Quality Process Step

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| allowOwnerToAddApprovers<br> | Boolean<br> | Determines if a step owner can add users to the step as approvers. Available only for steps of type SIGNOFF.<br> |
| approvals<br> | Array of References<br> | A reference to the approvals entered by approver users. Each value contains the attributes fullName and guid. Available only for steps of type SIGNOFF.<br> No approvals are shown in responses until all approver users have entered a decision<br> |
| assignee\*<br> | String<br> | The user to whom a step is assigned. Contains the attribute fullName. Deprecated as of Winter 2021 release.<br>DEPRECATED \- Please use assignees<br> |
| assignees<br> | Array of References<br> | A reference to the assignee of a Quality step. Lists users if assignee is a single user. Lists userGroups if assignee is a User Group.<br> |
| attributes<br> | Array of References<br> | A reference to the attributes on a step. Each value contains the attributes apiName, fieldType, guid, name, and value. Available only for steps of type REGULAR.<br> |
| completeDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a step was completed<br> |
| completeUser<br> | String<br> | The user who completed the step. Contains the attribute fullName.<br> |
| dueDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) the step must be completed NOTE: Only the date portion of this string is honored. Time always appears as 23:59:59 local time.<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| name<br> | String<br> | The name of a step<br> |
| order<br> | Integer<br> | The numeric value that determines a step's position in a process<br> |
| status<br> | Boolean<br> | The status of a Quality Process. Value can be OPEN or COMPLETE<br> |
| type<br> | Boolean<br> | Determines if a step includes approvals or not. Values are REGULAR and SIGNOFF. Default value is REGULAR.<br> |
| users<br> | String<br> | The user assigned to the Quality step. Also used to list the members of a User Group.<br> |
| userGroups<br> | String<br> | The User Group assigned to the quality step. Followed by an array of users that comprise the User Group.<br> |

No approvals are shown in responses until all approver users have entered a decision

