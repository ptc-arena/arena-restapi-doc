# Export Results: Sourcing Supplier Item Files
Sourcing Supplier Item File attributes are listed in the order that they appear in the CSV file..


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| parent<br> | Reference<br> | The Supplier Item that the source relationships is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes number, supplier name, supplier guid, guid, and name.<br> |
| file<br> | Reference<br> | The File associated with the Supplier Item. Includes name, location, number, edition, title, and strorageMethodName<br> |
| guid<br> | String<br> | The unique id of the Supplier Item File.<br> |
| primary<br> | True if primary file, else False<br> | Indicates whether or not a file is primary \(primary files are linked from the main view of objects to which they are associated.\)<br> |
| contentPath<br> | String<br> | Directory structure path to the location of the physical file in the export zip file.<br> |

