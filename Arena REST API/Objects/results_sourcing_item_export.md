# Export Results: Item Sourcing
Sourcing attributes are listed in the order that they appear in the CSV file..


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| parent  | Reference  | Item that the source relationships is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes GUID, revisionNumber, name, and Item.  |
| mfrItem  | Reference  | Details of the manufacturer Item. See Supplier Item object.  |
| vendorItem.number  | Reference  | Details of the vendor Item. See Supplier Item object.  |
| approved  | Boolean  | Indicates if a source relationship is approed. This value can be true or false.  |
| guid  | String  | The unique id for a source relationship.  |
| notes  | String  | The notes for a source relationship.  |
| activeProduction  | Boolean  | Indicates if a source relationship is the active production relationship. This value can be true or false.  |
| activePrototype  | Boolean  | Indicates if a source relationship is the active prototype relationship. This value can be true or false.  |
| amlRank  | Integer  | The AML rank. This value is numeric.  |
| amlSplit  | Integer  | The AM percentage.  |
| vendorItemConversionFactor  | String  | The conversion factor of the vendor item \(how many used per one bougt. e.g. for a roll of 100 resistors, wen you use one at a time, the conversion factor is 100\), For a Make-Item Source relationship, this must be null.,  |
| makeItem  | Boolean  | Indicates whether or not an item is made internally. This value can be true \(made internally\) or false \(made by supplier\).  |

