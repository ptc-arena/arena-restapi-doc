# Change
This object includes all fields in a Change.


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| additionalAttributes  | Array of Attributes  | The additional attributes of a change. This is an array of additional attributes. Each additional attribute entry includes a guid, a name, and a value.  |
| approvalDeadlineDateTime  | Date-Formatted String  | The date and time \(in Zulu format\) before which a change must be approved. If enforceApprovalDeadline is set to true, the change is automatically rejected once this deadline is passed.See the Note on Date/Time Handling  |
| category  | Reference  | The category of a change. This compact category listing includes guid, name, and path.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a change was created  |
| creator  | Reference  | The user that created the change. Includes email, fullName, and guid.  |
| description  | String  | The description of a change  |
| effectiveDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) when a change became effective  |
| effectivityPlannedDateTime  | Date-Formatted String  | The date and time when a change will become effective after approval. This is required only for changes of effectivityType PERMANENT_ON_DATE. See the Note on Date/Time Handling  |
| effectivityType  | String  | Indicates the type of effectivity for a change. Values can be PERMANENT_ON_APPROVAL, PERMANENT_ON_DATE, or TEMPORARY  |
| enforceApprovalDeadline  | Boolean  | Indicates whether or not the approval deadline of a change is enforced \(if a change with an enforced approval deadline reaches the deadline without being approved, it is automatically rejected.\) The value can be true or false. Note that if this value is true, approvalDeadlineDateTime must be specified.  |
| expirationDateTime  | Date-Formatted String  | The date and time when a change will expire. This is required only for changes of effectivityType TEMPORARY. Can be edited by any user when a change is in the Open and Unlocked lifecycle phase. Can be edited only by a Change Administrator user in the Effective or Submitted lifecycle phase.See the Note on Date/Time Handling  |
| guid  | String  | unique ID of a change  |
| implementationStatus  | String  | Impementation status of a change. Values can be NOT_STARTED, IN_PROGRESS, NEEDS_ATTENTION, DONE, or NONE.  |
| implementationStatusDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) the last implementation status edit occurred  |
| implementationStatusEditor  | Date-Formatted String  | The user who last edited the implementation status. Includes email, fullName, and guid.  |
| lifecycleDateTime  | String  | the date and time \(in Zulu format\) the last lifecycle phase change occurred  |
| lifecycleStatus  | String   | The lifecycle status of the change. Values can be OPEN_AND_UNLOCKED, OPEN_AND_LOCKED, SUBMITTED_FOR_ROUTING, SUBMITTED_FOR_APPROVAL, REJECTED, CANCELED, APPROVED, EFFECTIVE, COMPLETED, or EXPIRED.  |
| number  | String  | the number of a change  |
| routings  | Array of References  | The routings \(groups of users who vote\) included in the change. Includes guid and name.  |
| submissionDateTime  | String  | the date and time \(in Zulu format\) a change was submitted for approval  |
| submitter  | String  | the user who submitted the change for approval. Includes email, fullName, and guid.  |
| title  | String  | the title of a change  |
| url  | Array of References  | The direct urls of the object within the api and the application.  |

