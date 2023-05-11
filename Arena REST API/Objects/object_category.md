# Category

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| activated<br> | Boolean<br> | This indicates whether or not a category is activated for use in the workspace. The value should be true or false.<br> |
| allowDuplicateRevisions<br> | Boolean<br> | This indicates whether or not Items included in Changes of this category can use the same start and end revision. A value of True=allow reuse of revisions; a value of False=disallow reuse of revisions<br> |
| allowManualRevisionEntry<br> | Boolean<br> | This indicates whether or not users can manually enter an end revision for Items included in Changes of this category. A value of True=allow manual entry; a value of False=disallow manual entry.<br> |
| assignable<br> | Boolean<br> | This indicates that an Item can be assigned to the category. Categories can be assignable to an object if activated. True=assignable. False if not. Categories cannot be assignable if deactivated, deleted, or structural.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | The date and time \(in Zulu format\) an object was created.<br> |
| creator<br> | Reference<br> | The creator of a category. Contains the attributes email, fullName, and guid.<br> |
| description<br> | String<br> | The description of a category<br> |
| deletionDateTime<br> | Date\-Formatted String<br> | The date and time \(in Zulu format\) the category was deleted.<br> |
| effectivityType<br> | String<br> | The default effectivity type of a Change category. The value can be IMMEDIATE, FUTURE, or TEMPORARY. Temporary Changes in Arena are Deviations. \(only used for Change categories\)<br> |
| enforceDefaultEffectivityType<br> | Boolean<br> | This indicates whether or not the default effectivityType should be enforced for Changes assigned to this category. A value of True=default value is enforced. A value of False=default value is not enforced. When this is True, Changes assigned to the category must match the default effectivityType.<br> |
| enforceDefaultNumberSequence<br> | Boolean<br> | This indicates whether or not the default numberingSequence should be enforced for Changes assigned to this category. A value of True=default value is enforced. A value of False=default value is not enforced. When this is True, Changes assigned to the category must match the default numberingSequence.<br> |
| guid<br> | String<br> | The unique identifier for an object<br> |
| initialImplementationStatus<br> | String<br> | The starting implementation status for Changes assigned to the category.<br> |
| level<br> | Integer<br> | The depth in the category tree at which a category appears. For example: item\assembly has a level of 2, since the level of root category "item" is 1.<br> |
| name<br> | String<br> | The name of a category. For the system\-defined category \(root category\) for item, the name is "Item".<br> |
| numberFormat<br> | Reference<br> | Details of the number format associated with the category. See object. \(only used for Item categories\)<br>Item Number Format<br> |
| numberingSequencePrefixDefault<br> | Reference<br> | Details about the numbering sequence prefix used for Changes assigned to this category. \(only used for Change categories\)<br> |
| path<br> | String<br> | The path of a category, for example: item\assembly<br> |
| parentCategory<br> | Reference<br> | Details of the category that exists in a direct hierarchical relationship one order of magnitude higher than the category of the object.<br> |
| structural<br> | Boolean<br> | This indicates if a category is structural. Structural categories exist only to support the structure of the category tree \- no objects may be assigned to it directly. The value should be true if structural false if not structural.<br> |
| systemDefined<br> | Boolean<br> | This indicates if a category is system\-defined. The value should be true or false. Only "Item" is a system\-defined category.<br> |

