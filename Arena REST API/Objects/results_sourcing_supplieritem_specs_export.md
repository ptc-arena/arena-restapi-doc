# Export Results: Sourcing Supplier Item Specs
Sourcing Supplier Item Specs attributes are listed in the order that they appear in the CSV file..


| Field | Data Type | Description |
|  --- |  --- |  --- | 
| number | String | The supplier item number |
| supplier | Reference | Details of the Supplier. See Supplier object. |
| name | String | The supplier item name. |
| type | StringPart, Process, Document | The type of supplier item \(basic category\). This value can be PART, PROCESS, or DOCUMENT |
| uom | String | The unit of measure of the supplier item. |
| description | String | The description of a supplier item. |
| procurementType | String | Procurement Type. Can be OTS or MTS. |
| offTheShelf | Boolean | True if procurment Type is OTS, else False |
| guid | String | The unique id for the Supplier Item Specs |
| creationDateTime | Date\-Formatted String | The date and time \(in Zulu format\) the the Supplier Item was created. |
| creator | Reference | The creator of the Supplier Item. Includes fullName and email. |
| M4O7LIMOZGZ7Q5TR50LG | Custom attribute | Supplier Item custom attribute. |

