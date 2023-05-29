# Change
This object includes all fields in a Change.


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| additionalAttributes<br> | Array of Attributes<br> | The additional attributes of a change. This is an array of additional attributes. Each additional attribute entry includes a guid, a name, and a value.<br> |
| approvalDeadlineDateTime<br> | Date\-Formatted String<br> | The date and time \(in Zulu format\) before which a change must be approved. If enforceApprovalDeadline is set to true, the change is automatically rejected once this deadline is passed.See the<br>Note on Date/Time Handling<br> |
| category<br> | Reference<br> | The category of a change. This compact category listing includes guid, name, and path.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a change was created<br> |
| creator<br> | Reference<br> | The user that created the change. Includes email, fullName, and guid.<br> |
| description<br> | String<br> | The description of a change<br> |
| effectiveDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) when a change became effective<br> |
| effectivityPlannedDateTime<br> | Date\-Formatted String<br> | The date and time when a change will become effective after approval. This is required only for changes of effectivityType PERMANENT_ON_DATE. See the<br>Note on Date/Time Handling<br> |
| effectivityType<br> | String<br> | Indicates the type of effectivity for a change. Values can be PERMANENT_ON_APPROVAL, PERMANENT_ON_DATE, or TEMPORARY<br> |
| enforceApprovalDeadline<br> | Boolean<br> | Indicates whether or not the approval deadline of a change is enforced \(if a change with an enforced approval deadline reaches the deadline without being approved, it is automatically rejected.\) The value can be true or false. Note that if this value is true, approvalDeadlineDateTime must be specified.<br> |
| expirationDateTime<br> | Date\-Formatted String<br> | The date and time when a change will expire. This is required only for changes of effectivityType TEMPORARY. Can be edited by any user when a change is in the Open and Unlocked lifecycle phase. Can be edited only by a Change Administrator user in the Effective or Submitted lifecycle phase.See the<br>Note on Date/Time Handling<br> |
| guid<br> | String<br> | unique ID of a change<br> |
| implementationStatus<br> | String<br> | Impementation status of a change. Values can be NOT_STARTED, IN_PROGRESS, NEEDS_ATTENTION, DONE, or NONE.<br> |
| implementationStatusDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) the last implementation status edit occurred<br> |
| implementationStatusEditor<br> | Date\-Formatted String<br> | The user who last edited the implementation status. Includes email, fullName, and guid.<br> |
| lifecycleDateTime<br> | String<br> | the date and time \(in Zulu format\) the last lifecycle phase change occurred<br> |
| lifecycleStatus<br> | String<br> | The lifecycle status of the change. Values can be OPEN_AND_UNLOCKED, OPEN_AND_LOCKED, SUBMITTED_FOR_ROUTING, SUBMITTED_FOR_APPROVAL, REJECTED, CANCELED, APPROVED, EFFECTIVE, COMPLETED, or EXPIRED.<br> |
| number<br> | String<br> | the number of a change<br> |
| routings<br> | Array of References<br> | The routings \(groups of users who vote\) included in the change. Includes guid and name.<br> |
| submissionDateTime<br> | String<br> | the date and time \(in Zulu format\) a change was submitted for approval<br> |
| submitter<br> | String<br> | the user who submitted the change for approval. Includes email, fullName, and guid.<br> |
| title<br> | String<br> | the title of a change<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

