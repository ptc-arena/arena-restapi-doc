# Export Results: Item Files
File attributes are listed in the order that they appear in the CSV file..


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| parent<br> | Reference<br> | The Item that the File is associated with. The parent designation has no relation to BOM relationships in this specific context. Includes GUID, revisionNumber, name, and Item.<br> |
| file.name<br> | Reference<br> | The File associated with the Item. Includes name, file location, guid, nunber, edition, title, and storageMethodName.<br> |
| latestEditionAssociation<br> | Boolean<br> | Indicates whether or not a file is the latest edition. Can be true or false.<br> |
| primary<br> | Boolean<br> | Indicates whether or not a file is primary \(primary files are linked from the main view of objects to which they are associated.\)<br> |
| contentPath<br> | String<br> | Directory structure path to the location of the physical file in the export zip file.<br> |

