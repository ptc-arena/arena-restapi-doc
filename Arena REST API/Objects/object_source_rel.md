# Source Relationship

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| activeProduction | Boolean | Indicates if a source relationship is the active production relationship. This value can be true or false. |
| activePrototype | Boolean | Indicates if a source relationship is the active prototype relationship. This value can be true or false. |
| amlRank | Integer | The AML rank. This value is numeric. |
| approved | Boolean | Indicates if a source relationship is approved. This value can be true or false. |
| creationDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a source relationship was created |
| guid | String | The unique id for a source relationship |
| makeItem | Boolean | Indicates whether or not an item is made internally. This value can be true \(made internally\) or false \(made by supplier\) |
| mfrItem | Reference | Details of the manufacturer Item. See  object. |
| notes | String | The notes for a source relationship |
| vendorItem | Reference | Details of the vendor item. See  object. |
| vendorItem ConversionFactor | String | The conversion factor of the vendor item \(how many used per one bought. e.g. for a roll of 100 resistors, when you use one at a time, the conversion factor is 100\). For a Make\-Item Source Relationship, this must be null. |
| url | Array of References | The direct urls of the object within the api and the application. |

