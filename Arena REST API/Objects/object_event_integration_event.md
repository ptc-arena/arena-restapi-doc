# Event Queue: Integration Event

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| guid<br> | Reference<br> | The unique identifier for this particular event.<br> |
| ItemsReconciled<br> | Boolean<br> | Indicates if all Items in the event are reconciled. True or False only<br> |
| eventType<br> | String<br> | Identifies what caused the Event Items to become effective. Only possible VALUES are: CHANGE and REVISIONING_EVENT<br> |
| status<br> | String<br> | The status of the Integration Event. Possible values: UP_TO_DATE, DISABLED, IN_PROCESS, NEEDS_ATTENTION, NEEDS_UPDATE, UPDATES_QUEUED, and RECONCILED.<br> |
| creator<br> | Reference<br> | User who caused the event. Included fields: email, fullName, and guid.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | The date and time \(in Zulu format\) that this event was created.<br> |
| change<br> | Reference<br> | Only appears if eventType is CHANGE. Included fields: approvedOnDateTime, category, effectiveDateTime, effectivityType, guid, number, and title.<br> |
| revisioningEvent<br> | Reference<br> | Only appears if eventType is REVISIONING_EVENT. Included fields: guid, number, and performedOnDateTime.<br> |

