# Compliance Requirement

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| evidenceType<br> | String<br> | The type of evidence that proves the compliance status of an item or supplier item. The value can be NONE, DIRECT_FILES, AML_AND_FILES<br> |
| guid<br> | String<br> | the unique identifier of a compliance requirement<br> |
| lastModifiedBy<br> | String<br> | the user who last modified a compliance requirement<br> |
| lastModifiedDateTime<br> | Date-Formatted String<br> | the date and time \(in Zulu format\) a compliance requirement was last modified<br> |
| mark<br> | String<br> | the mark of a compliance requirement \(physical mark added to product or packaging\)<br> |
| propagate \(applies to Items only\)<br> | Boolean<br> | Indicates whether or not a compliance requirement is propagated to children. This value can be true or false.<br> |
| rationale<br> | String<br> | the rationale of a compliance requirement \(explanation of status\)<br> |
| requirement<br> | Reference<br> | Details of the requirement. See object.<br>Requirement<br> |
| status<br> | String<br> | The status of a compliance requirement. The value can be UNKNOWN, COMPLIANT, EXEMPT, NA, NON_COMPLIANT<br> |

