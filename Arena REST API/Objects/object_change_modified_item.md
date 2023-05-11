# Change Affected Item
Change Affected Items appear in  GET Change Item and GET Change Items responses and describe what modifications are being made to Items included in a Change, including new lifecycle phase and revision, inventory disposition information, and details about each view of the Item.


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| affectedItemRevision<br> | Reference<br> | Details of an affected item revision included in a change. This is the effective revision number. See object.<br>Revision<br> |
| bomView<br> | Reference<br> | Details about the BOM view of an item included in a change. See object<br>Item View<br> |
| dispositionAttributes<br> | Collection of References<br> | Details of the inventory disposition settings of an item \(e.g. In Design\). See object.<br>Disposition Attribute<br> |
| filesView<br> | Reference<br> | Details about the Files view of an item included in a change. See object<br>Item View<br> |
| guid<br> | String<br> | unique ID for a modified item<br> |
| materialEffectivityDateTime<br> | Date\-Formatted String<br> | date when inventory disposition settings for a change become effective<br> |
| newItemRevision<br> | Reference<br> | Details of the item revision entered on the Specs view of the working revision in the Items world. See object.<br>Revision<br> |
| newRevisionNumber<br> | Reference<br> | Details of the item revision that will be released by a change. \(The value on the Specs view of the working revision in the Items world\). See object.<br>Revision<br> |
| newLifecyclePhase<br> | Reference<br> | Details of the target lifecycle phase for an item included in a change<br> |
| retraining<br> | String<br> | Available for Change Affected Items that are also part of Training Plans. Possible values: NO_RETRAIN; AFTER_APPROVED; AFTER_EFFECTIVE<br> |
| retrainingRequired<br> | Boolean<br> | Indicates that the Change Affected Item has a retrain option for After Approval or After Affective<br> |
| sourcingView<br> | Reference<br> | Details about the Sourcing view of an item included in a change. See object.<br>Item View<br> |
| specsView<br> | Reference<br> | Details about the Specs view of an item included in a change. See object.<br>Item View<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

