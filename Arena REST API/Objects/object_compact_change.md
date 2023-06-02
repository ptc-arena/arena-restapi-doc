# Change Compact

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| category  | Reference  | The category of a change. This compact category listing includes guid, name, and path.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a change was created  |
| creator  | Reference  | The user that created the change. Includes email, fullName, and guid.  |
| effectiveDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) when a change became effective  |
| guid  | String  | unique ID of a change  |
| implementationStatus  | String  | Impementation status of a change. Values can be NOT_STARTED, IN_PROGRESS, NEEDS_ATTENTION, DONE, or NONE.  |
| lifecycleDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) the last lifecycle phase change occurred  |
| lifecycleStatus  | String   | The lifecycle status of the change. Values can be OPEN_AND_UNLOCKED, OPEN_AND_LOCKED, SUBMITTED_FOR_ROUTING, SUBMITTED_FOR_APPROVAL, REJECTED, CANCELED, APPROVED, EFFECTIVE, COMPLETED, or EXPIRED.  |
| number  | String  | the number of a change  |
| submissionDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a change was submitted for approval  |
| title  | String  | the title of a change  |
| url  | Array of References  | The direct urls of the object within the api and the application  |

