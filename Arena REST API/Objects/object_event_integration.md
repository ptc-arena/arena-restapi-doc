# Event Queue: Integration Information

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| guid<br> | String<br> | The unique id for the Integration. Currently only outbound integrations are supported.<br> |
| name<br> | String<br> | The name of the Integration.<br> |
| status<br> | String<br> | The status of the Integration. Possible values: UP_TO_DATE, DISABLED, IN_PROCESS, NEEDS_ATTENTION, NEEDS_UPDATE, UPDATES_QUEUED, and RECONCILED.<br> |
| type<br> | String<br> | The integration type. Currently only OUTBOUND_AUTOMATED and OUTBOUND_MANAGED are supported.<br> |
| transferType<br> | String<br> | The type of transfer being performed. Currently only ITEM_REVISION and CHANGE is supported<br> |
| integrationUser<br> | Reference<br> | Integration user information. fullName, guid, and email included.<br> |
| enabled<br> | Boolean<br> | Determines whether Integration is enabled or disabled. Enabled is true; disabled is false.<br> |
| creator<br> | Reference<br> | User account information on the creator of the Integration. Includes: fullName, guid, and email.<br> |
| creationDateTime<br> | Date-Formatted String<br> | The date and time \(in Zulu format\) the the Integration was created.<br> |
| modifyUser<br> | Reference<br> | User who last modified the Integration. Included: fullName, guid and email.<br> |
| modifyDateTime<br> | Date-Formatted String<br> | The date and time \(in Zulu format\) that the integration was last modified.<br> |

