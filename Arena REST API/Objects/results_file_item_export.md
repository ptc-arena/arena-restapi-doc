# Export Results: Item Files
File attributes are listed in the order that they appear in the CSV file..


| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| parent  | Reference  | The Item that the File is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes GUID, revisionNumber, name, and Item.  |
| file.name  | Reference  | The File associated with the Item. Includes name, file location, guid, nunber, edition, title, and storageMethodName.  |
| latestEditionAssociation  | Boolean  | Indicates whether or not a file is the latest edition. Can be true or false.  |
| primary  | Boolean  | Indicates whether or not a file is primary \(primary files are linked from the main view of objects to which they are associated.\)  |
| contentPath  | String  | Directory structure path to the location of the physical file in the export zip file.  |

