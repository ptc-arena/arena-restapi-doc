# Quality Process

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| completedDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a Quality Process was completed |
| creationDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a Quality Process was created |
| creator | Reference | The user who created the Quality Process. Contains the atrributes fullName and guid. |
| currentStep | Reference | Details of the current step of the Quality Process. This listing includes the attributes approvals \(null unless sign\-off step\), attributes, and guid. |
| description | String | The description of a template |
| guid | String | The unique identifier for an object |
| name | String | The name of a Quality Process |
| number | String | The number of a Quality Process |
| owner | Reference | The name of the user who owns the Quality Process. Contains the attributes fullName and guid. |
| status | Boolean | The status of a Quality Process. Value can be OPEN or COMPLETE. |
| statusMode | Boolean | The mode by which the status attribute advances from OPEN to COMPLETE. Value can be AUTOMATIC or MANUAL. Default value is MANUAL. |
| targetCompletionDate | Date\-Formatted String | The date a Quality Process is targeted for completion |
| template | Reference | Details of the template upon which a process was based. Contains the attributes active and guid. |
| type | String | The type of the Quality Process. NOTE this always returns null. |

