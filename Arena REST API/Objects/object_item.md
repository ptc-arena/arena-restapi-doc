# Item

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| additionalAttributes  | Array of Attributes  | The additional attributes of an item. Each additional attribute entry contains apiName, fieldType, guid, name, and value.   |
| assemblyType  | String  | Determines if an item is an assembly, not an assembly, or a top level assembly. Top level assemblies are items that contain other items in its own bill of materials but themselves are not included as an item in another item's bill of materials.  |
| category  | Reference  | GUID of the category to which the item is assigned. See Category object.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) an item was created  |
| creator  | Reference  | The creator of an item. Contains the email and fullName.  |
| description  | String  | The description of an item  |
| deviated  | Boolean  | Indicates whether or not an item is currently affected by a temporary change. The value can be true or false.  |
| effectiveDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) the effective revision of an item was made effective.  |
| guid  | String  | The unique identifier for an object  |
| isAssembly  | Boolean  | Indicates whether or not an item is an assembly. The value can be true or false.  |
| inAssembly  | Boolean  | Determines if an item is in an assembly. Values can be true or false.  |
| lifecyclePhase  | Reference  | The lifecycle phase of an item \(e.g. In Design\). Contains GUID and name. See Item Lifecycle Phase object.  |
| name  | String  | The name of an item  |
| modifiedBom  | Boolean  | Indicates whether or not the BOM view of an item contains working modifications. The value can be true or false.  |
| modifiedFiles  | Boolean  | Indicates whether or not the Files view of an item contains working modifications. The value can be true or false.  |
| modifiedSourcing  | Boolean  | Indicates whether or not the Sourcing view of an item contains working modifications. The value can be true or false.  |
| modifiedSpecs  | Boolean  | Indicates whether or not the Specs view of an item contains working modifications. The value can be true or false.  |
| name  | String  | The name of an item  |
| number  | String  | The number of an item  |
| offTheShelf\*  | Boolean  | **DEPRECATED - Please use procurementType** Indicates whether or not an item's Procurement Type is off the shelf. The value can be true or false.  |
| owner  | Reference  | The owner of an item. Contains fullName.  |
| procurementType  | String  | Indicates whether an Item is Off the Shelf \(OTS\) or Made to Specification \(MTS\).  |
| productionCost  | Double  | The production cost of an item  |
| prototypeCost  | Double  | The prototype cost of an item  |
| revisionNumber  | String  | The revision of an item  |
| revisionStatus  | String  | The status of an Item revision. This value can be WORKING, EFFECTIVE, or SUPERSEDED. See status.  |
| shared  | Boolean  | Indicates whether or not an item is shared with suppliers. The value can be true or false.  |
| status\*  | Integer  | **DEPRECATED - Please use revisionStatus** The status of an item revision. This value can be 0 \(working revision\), 1 \(effective\) or 2 \(superseded\).  |
| standardCost  | Double  | The standard cost of an item  |
| supersededDateTime  | Date-Formatted String  | The date and time upon which a revision became superseded \(no longer the effective revision\). Null unless you are returning a superseded revision.  |
| targetCost  | Double  | The target cost of an item  |
| targetPrice  | Double  | The target price of an item  |
| uom  | String  | The unit of measure of an item  |
| url  | Array of References  | The direct urls of the object within the api and the application.  |

