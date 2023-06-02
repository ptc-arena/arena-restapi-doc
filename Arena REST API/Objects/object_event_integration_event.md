# Event Queue: Integration Event

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| guid  | Reference  | The unique identifier for this particular event.  |
| ItemsReconciled  | Boolean  | Indicates if all Items in the event are reconciled. True or False only  |
| eventType  | String  | Identifies what caused the Event Items to become effective. Only possible VALUES are: CHANGE and REVISIONING_EVENT  |
| status  | String  | The status of the Integration Event. Possible values: UP_TO_DATE, DISABLED, IN_PROCESS, NEEDS_ATTENTION, NEEDS_UPDATE, UPDATES_QUEUED, and RECONCILED.  |
| creator  | Reference  | User who caused the event. Included fields: email, fullName, and guid.  |
| creationDateTime  | Date-Formatted String  | The date and time \(in Zulu format\) that this event was created.   |
| change  | Reference  | Only appears if eventType is CHANGE. Included fields: approvedOnDateTime, category, effectiveDateTime, effectivityType, guid, number, and title.  |
| revisioningEvent  | Reference  | Only appears if eventType is REVISIONING_EVENT. Included fields: guid, number, and performedOnDateTime.  |

