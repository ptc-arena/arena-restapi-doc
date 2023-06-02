# Change Affected Item
Change Affected Items appear in  GET Change Item and GET Change Items responses and describe what modifications are being made to Items included in a Change, including new lifecycle phase and revision, inventory disposition information, and details about each view of the Item.


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| affectedItemRevision  | Reference  | Details of an affected item revision included in a change. This is the effective revision number. See Revision object.  |
| bomView  | Reference  | Details about the BOM view of an item included in a change. See Item View object  |
| dispositionAttributes  | Collection of References  | Details of the inventory disposition settings of an item \(e.g. In Design\). See Disposition Attribute object.  |
| filesView  | Reference  | Details about the Files view of an item included in a change. See Item View object  |
| guid  | String  | unique ID for a modified item  |
| materialEffectivityDateTime  | Date-Formatted String  | date when inventory disposition settings for a change become effective  |
| newItemRevision  | Reference  | Details of the item revision entered on the Specs view of the working revision in the Items world. See Revision object.  |
| newRevisionNumber  | Reference  | Details of the item revision that will be released by a change. \(The value on the Specs view of the working revision in the Items world\). See Revision object.  |
| newLifecyclePhase  | Reference  | Details of the target lifecycle phase for an item included in a change  |
| retraining  | String  | Available for Change Affected Items that are also part of Training Plans. Possible values: NO_RETRAIN; AFTER_APPROVED; AFTER_EFFECTIVE  |
| retrainingRequired  | Boolean  | Indicates that the Change Affected Item has a retrain option for After Approval or After Affective  |
| sourcingView  | Reference  | Details about the Sourcing view of an item included in a change. See Item View object.  |
| specsView  | Reference  | Details about the Specs view of an item included in a change. See Item View object.  |
| url  | Array of References  | The direct urls of the object within the api and the application.  |

