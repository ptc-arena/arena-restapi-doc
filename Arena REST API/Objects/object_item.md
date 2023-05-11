# Item

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| additionalAttributes<br> | Array of Attributes<br> | The additional attributes of an item. Each additional attribute entry contains apiName, fieldType, guid, name, and value.<br> |
| assemblyType<br> | String<br> | Determines if an item is an assembly, not an assembly, or a top level assembly. Top level assemblies are items that contain other items in its own bill of materials but themselves are not included as an item in another item's bill of materials.<br> |
| category<br> | Reference<br> | GUID of the category to which the item is assigned. See object.<br>Category<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) an item was created<br> |
| creator<br> | Reference<br> | The creator of an item. Contains the email and fullName.<br> |
| description<br> | String<br> | The description of an item<br> |
| deviated<br> | Boolean<br> | Indicates whether or not an item is currently affected by a temporary change. The value can be true or false.<br> |
| effectiveDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) the effective revision of an item was made effective.<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| isAssembly<br> | Boolean<br> | Indicates whether or not an item is an assembly. The value can be true or false.<br> |
| inAssembly<br> | Boolean<br> | Determines if an item is in an assembly. Values can be true or false.<br> |
| lifecyclePhase<br> | Reference<br> | The lifecycle phase of an item \(e.g. In Design\). Contains GUID and name. See object.<br>Item Lifecycle Phase<br> |
| name<br> | String<br> | The name of an item<br> |
| modifiedBom<br> | Boolean<br> | Indicates whether or not the BOM view of an item contains working modifications. The value can be true or false.<br> |
| modifiedFiles<br> | Boolean<br> | Indicates whether or not the Files view of an item contains working modifications. The value can be true or false.<br> |
| modifiedSourcing<br> | Boolean<br> | Indicates whether or not the Sourcing view of an item contains working modifications. The value can be true or false.<br> |
| modifiedSpecs<br> | Boolean<br> | Indicates whether or not the Specs view of an item contains working modifications. The value can be true or false.<br> |
| name<br> | String<br> | The name of an item<br> |
| number<br> | String<br> | The number of an item<br> |
| offTheShelf\*<br> | Boolean<br> | Indicates whether or not an item's Procurement Type is off the shelf. The value can be true or false.<br>DEPRECATED \- Please use procurementType<br> |
| owner<br> | Reference<br> | The owner of an item. Contains fullName.<br> |
| procurementType<br> | String<br> | Indicates whether an Item is Off the Shelf \(OTS\) or Made to Specification \(MTS\).<br> |
| productionCost<br> | Double<br> | The production cost of an item<br> |
| prototypeCost<br> | Double<br> | The prototype cost of an item<br> |
| revisionNumber<br> | String<br> | The revision of an item<br> |
| revisionStatus<br> | String<br> | The status of an Item revision. This value can be WORKING, EFFECTIVE, or SUPERSEDED. See status.<br> |
| shared<br> | Boolean<br> | Indicates whether or not an item is shared with suppliers. The value can be true or false.<br> |
| status\*<br> | Integer<br> | The status of an item revision. This value can be 0 \(working revision\), 1 \(effective\) or 2 \(superseded\).<br>DEPRECATED \- Please use revisionStatus<br> |
| standardCost<br> | Double<br> | The standard cost of an item<br> |
| supersededDateTime<br> | Date\-Formatted String<br> | The date and time upon which a revision became superseded \(no longer the effective revision\). Null unless you are returning a superseded revision.<br> |
| targetCost<br> | Double<br> | The target cost of an item<br> |
| targetPrice<br> | Double<br> | The target price of an item<br> |
| uom<br> | String<br> | The unit of measure of an item<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

