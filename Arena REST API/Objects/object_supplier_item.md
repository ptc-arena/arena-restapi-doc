# Supplier Item

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| additionalAttributes  | Array of Attributes  | The additional attributes of an item. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute.  |
| creationDateTime\*  | Date-Formatted String  | **DEPRECATED** the date and time \(in Zulu format\) a supplier item was created.   |
| Description  | String  | The description of a supplier item  |
| guid  | String  | The unique id for a supplier item  |
| name  | String  | The supplier item name  |
| number  | String  | The supplier item number  |
| offTheShelf  | Boolean  | Indicates whether or not the procurement type of the supplier item is off the shelf. This value can be true \(off-the-shelf\) or false \(made-to-spec\).  |
| supplier  | Reference  | Details of the supplier. See Supplier object.  |
| type  | String  | The type of supplier item \(basic category\). This value can be PART, PROCESS, or DOCUMENT.  |
| uom  | String  | The unit of measure of the supplier item  |

