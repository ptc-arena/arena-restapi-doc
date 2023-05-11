# Event Queue: Integration Event Items

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| guid<br> | String<br> | The unique identifier for this particular event Item.<br> |
| effectiveItemRevision<br> | Reference<br> | The effective revision of the Event Item. Includes: guid, number, revisionNumber, lifecyclePhase, modifiedBOM, modifiedFiles, modifiedSourcing, and modifiedSpecs.<br> |
| supersededItemRevision<br> | Reference<br> | The superseded revision of the Event Item. Includes: guid, number, revisionNumber, lifecyclePhase, modifiedBOM, modifiedFiles, modifiedSourcing, and modifiedSpecs.<br> |
| reconciled<br> | Boolean<br> | Indicates whether an event Item is reconciled or not. True or False values only.<br> |
| reconciledDateTime<br> |   | The date and time \(in Zulu format\) when the event Item was reconciled.<br> |
| reconcileUser<br> | Reference<br> | The user who reconciled the Item. Included fields: guid, fullName, and email.<br> |

