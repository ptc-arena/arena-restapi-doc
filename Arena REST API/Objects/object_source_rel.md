# Source Relationship

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| activeProduction<br> | Boolean<br> | Indicates if a source relationship is the active production relationship. This value can be true or false.<br> |
| activePrototype<br> | Boolean<br> | Indicates if a source relationship is the active prototype relationship. This value can be true or false.<br> |
| amlRank<br> | Integer<br> | The AML rank. This value is numeric.<br> |
| approved<br> | Boolean<br> | Indicates if a source relationship is approved. This value can be true or false.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a source relationship was created<br> |
| guid<br> | String<br> | The unique id for a source relationship<br> |
| makeItem<br> | Boolean<br> | Indicates whether or not an item is made internally. This value can be true \(made internally\) or false \(made by supplier\)<br> |
| mfrItem<br> | Reference<br> | Details of the manufacturer Item. See object.<br>Supplier Item<br> |
| notes<br> | String<br> | The notes for a source relationship<br> |
| vendorItem<br> | Reference<br> | Details of the vendor item. See object.<br>Supplier Item<br> |
| vendorItem ConversionFactor<br> | String<br> | The conversion factor of the vendor item \(how many used per one bought. e.g. for a roll of 100 resistors, when you use one at a time, the conversion factor is 100\). For a Make\-Item Source Relationship, this must be null.<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

