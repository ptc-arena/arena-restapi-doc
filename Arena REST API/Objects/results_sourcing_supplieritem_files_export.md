# Export Results: Sourcing Supplier Item Files
Sourcing Supplier Item File attributes are listed in the order that they appear in the CSV file..


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| parent  | Reference  | The Supplier Item that the source relationships is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes number, supplier name, supplier guid, guid, and name.  |
| file  | Reference  | The File associated with the Supplier Item. Includes name, location, number, edition, title, and strorageMethodName  |
| guid  | String  | The unique id of the Supplier Item File.  |
| primary  | True if primary file, else False  | Indicates whether or not a file is primary \(primary files are linked from the main view of objects to which they are associated.\)  |
| contentPath  | String  | Directory structure path to the location of the physical file in the export zip file.  |

