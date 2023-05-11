# Item Compact

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| assemblyType<br> | String<br> | Determines if an item is an assembly, not an assembly, or a top level assembly. Top level assemblies are items that contain other items in its own bill of materials but themselves are not included as an item in another item's bill of materials.<br> |
| category<br> | Reference<br> | GUID representing the category to which the item is assigned. See object.<br>Category<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) an Item was created<br> |
| effectiveDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) an Item \(specifically an item revision\) became effective.<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| inAssembly<br> | Boolean<br> | Determines if an item is in an assembly. Values can be true or false.<br> |
| lifecyclePhase<br> | Reference<br> | GUID and name of the lifecycle phase of an item \(e.g. In Design\). See object.<br>Item Lifecycle Phase<br> |
| name<br> | String<br> | The name of an item<br> |
| number<br> | String<br> | The number of an item<br> |
| revisionNumber<br> | String<br> | The revision of an item<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

