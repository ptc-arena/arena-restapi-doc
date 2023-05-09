# Export Results: Item Specs 
Item Specs attributes that are included in the SPECS CSV of the Export.


| Field | Data Type | Description |
|  --- |  --- |  --- | 
| number | String | Item Number.  |
| guid | String | The unique identifier for an object |
| revisionNumber | String | Revision |
| name | String | Item Name |
| lifecyclePhase | Reference | The lifecycle phase of an Item |
| category | Reference | The category of an Item |
|  description | String | The description of an Item |
| uom | String | The unit of measure for an Item |
| procurementType | String | OTS and MTS only |
| offTheShelf | Boolean | True if procurementType=OTS, else False |
| owner | Reference | The owner of an Item |
| creationDateTime | Date\-Formatted String | The date and time \(in Zulu format\) an Item was created. |
| shared | Boolean | Indicates whether or not an item is shared with Suppliers. The value can be true or false |
| creator | Reference | The creator of an Item. Contains the email and fullName |
| deviated | Boolean | Indicates whether or not an Item is currently affected by a temporary change. The value can be true or false. |
| effectiveDateTime | Date\-Formatted String | The date and time \(in Zulu format\) an Item was made effective |
| isAssembly | Boolean  | Indicates whether or not an item is in an assembly. The value can be true or false |
| modifiedBOM | Boolean | Indicates whether or not the BOM view of an item contains working modifications. The value can be true or false |
| modifiedFiles | Boolean | Indicates whether or not the Files view of an item contains working modifications. The value can be true or false. |
| modifiedSourcing | Boolean | Indicates whether or not the Sourcing view of an item contains working modifications. The value can be true or false. |
| modifiedSpecs | Boolean | Indicates whether or not the Specs view of an item contains working modifications. The value can be true or false. |
| modifiedCosting | Boolean | Indicates whether or not the Costing view of an item contains working modifications. The value can be true or false. |
| productionCost | Double | The production cost of an Item. |
| prototypeCost | Double | The prototype cost of an Item. |
| targetCost | Double | The target cost of an Item. |
| targetPrice | Double | The target price of an Item. |
| standardCost | Double | The standard cost of an Item. |
| revisionStatus | String | The Revision status of an Item. WORKING, EFFECTIVE, SUPERSEDED |
| supersededDateTime | In Zulu format | The date and time \(in Zulu format\) an Item was superseded. |
| M4O7LIMOZGZ7Q5TR50LG | Custom Attribute | An Item custom attribute. |

