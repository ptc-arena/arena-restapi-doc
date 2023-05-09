# Event Queue: Integration Event Items

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| guid | String | The unique identifier for this particular event Item. |
| effectiveItemRevision | Reference | The effective revision of the Event Item. Includes: guid, number, revisionNumber, lifecyclePhase, modifiedBOM, modifiedFiles, modifiedSourcing, and modifiedSpecs. |
| supersededItemRevision | Reference | The superseded revision of the Event Item. Includes: guid, number, revisionNumber, lifecyclePhase, modifiedBOM, modifiedFiles, modifiedSourcing, and modifiedSpecs. |
| reconciled | Boolean | Indicates whether an event Item is reconciled or not. True or False values only. |
| reconciledDateTime |   | The date and time \(in Zulu format\) when the event Item was reconciled. |
| reconcileUser | Reference | The user who reconciled the Item. Included fields: guid, fullName, and email.  |

