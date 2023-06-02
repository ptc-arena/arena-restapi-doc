# Event Queue: Integration Information

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| guid  | String  | The unique id for the Integration. Currently only outbound integrations are supported.  |
| name  | String  | The name of the Integration.  |
| status  | String  | The status of the Integration. Possible values: UP_TO_DATE, DISABLED, IN_PROCESS, NEEDS_ATTENTION, NEEDS_UPDATE, UPDATES_QUEUED, and RECONCILED.  |
| type  | String  | The integration type. Currently only OUTBOUND_AUTOMATED and OUTBOUND_MANAGED are supported.  |
| transferType  | String  | The type of transfer being performed. Currently only ITEM_REVISION and CHANGE is supported  |
| integrationUser  | Reference  | Integration user information. fullName, guid, and email included.  |
| enabled  | Boolean  | Determines whether Integration is enabled or disabled. Enabled is true; disabled is false.  |
| creator  | Reference  | User account information on the creator of the Integration. Includes: fullName, guid, and email.  |
| creationDateTime  | Date-Formatted String  | The date and time \(in Zulu format\) the the Integration was created.  |
| modifyUser  | Reference  | User who last modified the Integration. Included: fullName, guid and email.  |
| modifyDateTime  | Date-Formatted String  | The date and time \(in Zulu format\) that the integration was last modified.  |

