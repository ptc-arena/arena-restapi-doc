# Supplier Item

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| additionalAttributes<br> | Array of Attributes<br> | The additional attributes of an item. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute.<br> |
| creationDateTime\*<br> | Date-Formatted String<br> | the date and time \(in Zulu format\) a supplier item was created.<br>**DEPRECATED** |
| Description<br> | String<br> | The description of a supplier item<br> |
| guid<br> | String<br> | The unique id for a supplier item<br> |
| name<br> | String<br> | The supplier item name<br> |
| number<br> | String<br> | The supplier item number<br> |
| offTheShelf<br> | Boolean<br> | Indicates whether or not the procurement type of the supplier item is off the shelf. This value can be true \(off-the-shelf\) or false \(made-to-spec\).<br> |
| supplier<br> | Reference<br> | Details of the supplier. See object.<br>Supplier<br> |
| type<br> | String<br> | The type of supplier item \(basic category\). This value can be PART, PROCESS, or DOCUMENT.<br> |
| uom<br> | String<br> | The unit of measure of the supplier item<br> |

