# Export Results: Item Sourcing
Sourcing attributes are listed in the order that they appear in the CSV file..


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| parent<br> | Reference<br> | Item that the source relationships is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes GUID, revisionNumber, name, and Item.<br> |
| mfrItem<br> | Reference<br> | Details of the manufacturer Item. See Supplier Item object.<br> |
| vendorItem.number<br> | Reference<br> | Details of the vendor Item. See Supplier Item object.<br> |
| approved<br> | Boolean<br> | Indicates if a source relationship is approed. This value can be true or false.<br> |
| guid<br> | String<br> | The unique id for a source relationship.<br> |
| notes<br> | String<br> | The notes for a source relationship.<br> |
| activeProduction<br> | Boolean<br> | Indicates if a source relationship is the active production relationship. This value can be true or false.<br> |
| activePrototype<br> | Boolean<br> | Indicates if a source relationship is the active prototype relationship. This value can be true or false.<br> |
| amlRank<br> | Integer<br> | The AML rank. This value is numeric.<br> |
| amlSplit<br> | Integer<br> | The AM percentage.<br> |
| vendorItemConversionFactor<br> | String<br> | The conversion factor of the vendor item \(how many used per one bougt. e.g. for a roll of 100 resistors, wen you use one at a time, the conversion factor is 100\), For a Make-Item Source relationship, this must be null.,<br> |
| makeItem<br> | Boolean<br> | Indicates whether or not an item is made internally. This value can be true \(made internally\) or false \(made by supplier\).<br> |

