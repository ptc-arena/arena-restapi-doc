# Compliance Requirement

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| evidenceType  | String  | The type of evidence that proves the compliance status of an item or supplier item. The value can be NONE, DIRECT_FILES, AML_AND_FILES  |
| guid  | String  | the unique identifier of a compliance requirement  |
| lastModifiedBy  | String  | the user who last modified a compliance requirement  |
| lastModifiedDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a compliance requirement was last modified  |
| mark  | String  | the mark of a compliance requirement \(physical mark added to product or packaging\)  |
| propagate \(applies to Items only\)  | Boolean  | Indicates whether or not a compliance requirement is propagated to children. This value can be true or false.  |
| rationale  | String  | the rationale of a compliance requirement \(explanation of status\)  |
| requirement  | Reference  | Details of the requirement. See Requirement object.  |
| status  | String  | The status of a compliance requirement. The value can be UNKNOWN, COMPLIANT, EXEMPT, NA, NON_COMPLIANT  |

