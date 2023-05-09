# Category

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| activated | Boolean | This indicates whether or not a category is activated for use in the workspace. The value should be true or false. |
| allowDuplicateRevisions | Boolean | This indicates whether or not Items included in Changes of this category can use the same start and end revision. A value of True=allow reuse of revisions; a value of False=disallow reuse of revisions |
| allowManualRevisionEntry | Boolean | This indicates whether or not users can manually enter an end revision for Items included in Changes of this category. A value of True=allow manual entry; a value of False=disallow manual entry. |
| assignable | Boolean | This indicates that an Item can be assigned to the category. Categories can be assignable to an object if activated. True=assignable. False if not. Categories cannot be assignable if deactivated, deleted, or structural. |
| creationDateTime | Date\-Formatted String | The date and time \(in Zulu format\) an object was created. |
| creator | Reference | The creator of a category. Contains the attributes email, fullName, and guid. |
| description | String | The description of a category |
| deletionDateTime | Date\-Formatted String | The date and time \(in Zulu format\) the category was deleted. |
| effectivityType | String | The default effectivity type of a Change category. The value can be IMMEDIATE, FUTURE, or TEMPORARY. Temporary Changes in Arena are Deviations. \(only used for Change categories\) |
| enforceDefaultEffectivityType | Boolean | This indicates whether or not the default effectivityType should be enforced for Changes assigned to this category. A value of True=default value is enforced. A value of False=default value is not enforced. When this is True, Changes assigned to the category must match the default effectivityType. |
| enforceDefaultNumberSequence | Boolean | This indicates whether or not the default numberingSequence should be enforced for Changes assigned to this category. A value of True=default value is enforced. A value of False=default value is not enforced. When this is True, Changes assigned to the category must match the default numberingSequence. |
| guid | String | The unique identifier for an object |
| initialImplementationStatus | String | The starting implementation status for Changes assigned to the category. |
| level | Integer | The depth in the category tree at which a category appears. For example: item\assembly has a level of 2, since the level of root category "item" is 1. |
| name | String | The name of a category. For the system\-defined category \(root category\) for item, the name is "Item". |
| numberFormat | Reference | Details of the number format associated with the category. See  object. \(only used for Item categories\) |
| numberingSequencePrefixDefault | Reference | Details about the numbering sequence prefix used for Changes assigned to this category. \(only used for Change categories\) |
| path | String | The path of a category, for example: item\assembly |
| parentCategory | Reference | Details of the category that exists in a direct hierarchical relationship one order of magnitude higher than the category of the object. |
| structural | Boolean | This indicates if a category is structural. Structural categories exist only to support the structure of the category tree \- no objects may be assigned to it directly. The value should be true if structural false if not structural. |
| systemDefined | Boolean | This indicates if a category is system\-defined. The value should be true or false. Only "Item" is a system\-defined category. |

