# Import Engine Mapping
Import Engine mapping maps the source file attribute name to the Arena API name.

The mapping can include each attribute that can be imported.

The mapping consists of:


| Mapping Component | Description | Example | Required |
|  --- |  --- |  --- |  --- | 
| resourceName | Resource Name | ITEM_BOM | Yes |
| apiName | API name for attribute | category.name | Yes |
| sourceName | Source name for atribute | Category Name | Yes |
| InResponse | True to return the attribute in the resposne content. False to exclue the arrtibute in the response Content. | TRUE | No. True if omitted. |
| notes | Notes for user. Not used for processing. | "This is a custom attribute." | No |

API names represented by objects \(such as category\) are specified by the attribute object name, a period, and the object's attribute.  Examples of this are the following: category.name, category.path, lifecyclePhase.guid, owner.fullName, etc.

Custom attributes \(also known as additional attributes\) can also be mapped. The API name for a custom attribute is the attribute name. For example, if an item custom attribute is "Tolerance", then the apiName is "Tolerance".

All resource, apiName, and sourceName values are case insensitive.

