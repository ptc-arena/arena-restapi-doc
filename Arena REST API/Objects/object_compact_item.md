# Item Compact

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| assemblyType | String | Determines if an item is an assembly, not an assembly, or a top level assembly. Top level assemblies are items that contain other items in its own bill of materials but themselves are not included as an item in another item's bill of materials. |
| category | Reference | GUID representing the category to which the item is assigned. See  object. |
| creationDateTime | Date\-Formatted String | the date and time \(in Zulu format\) an Item was created |
| effectiveDateTime | Date\-Formatted String | the date and time \(in Zulu format\) an Item \(specifically an item revision\) became effective. |
| guid | String | The unique identifier for an object  |
| inAssembly | Boolean | Determines if an item is in an assembly. Values can be true or false. |
| lifecyclePhase | Reference | GUID and name of the lifecycle phase of an item \(e.g. In Design\). See  object. |
| name | String | The name of an item |
| number | String | The number of an item |
| revisionNumber | String | The revision of an item |
| url | Array of References | The direct urls of the object within the api and the application. |

