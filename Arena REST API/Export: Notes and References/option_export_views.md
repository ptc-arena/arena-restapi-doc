# Export Options
Export options determine what Item views and attributes are included in an export.

Export Views table displays which views of an Item can be included in an export.


| exportViews<br> | Description<br> |
|  --- |  --- | 
| SPECS<br> | Specs data for all Items.<br> |
| BOM<br> | BOM Lines for all Items<br> |
| BOM_SUBSTITUTES<br> | BOM Substitutes for all Items<br> |
| SOURCING<br> | Sourcing relationships for all Items<br> |
| FILES<br> | File Associations for all Items<br> |
| FILES_FILE_SUMMARY<br> | File summary for all Files on Item Files<br> |
| SOURCING_SUPPLIERITEM_SPECS<br> | Supplier Item Specs for all Supplier Items on Item sourcing<br> |
| SOURCING_SUPPLIERITEM_SUPPLIER_PROFILE<br> | Supplier Profile for all Supplier Items on Item sourcing<br> |
| SOURCING_SUPPLIERITEM_FILES<br> | Supplier Item File associations for all Supplier Items in Sourcing<br> |
| SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY<br> | File summary for all files on Supplier Items on Item Sourcing<br> |

File Content determines if the actual Files associated with Items and Supplier Items are included within the export. Assigning a value of PRIMARY to fileContent is not supported for supplierItem.


| fileContent<br> | Description<br> |
|  --- |  --- | 
| NONE<br> | Export does not include any physical files. Can be used for Items and Supplier Items.<br> |
| PRIMARY<br> | Export includes only the Primary physical Files. Can be used ONLY for Items.<br> |
| ALL<br> | Export includes all Files. Can be used for Items and Supplier Items.<br> |

BOM Levels adds children Items on the BOM of matching Items to the results.


| bomLevels<br> | Description<br> |
|  --- |  --- | 
| NONE<br> | Does not add child Items to the results<br> |
| SINGLE<br> | Adds the Items on the single level BOM of matching Items to the results<br> |
| FULL<br> | Add s the Items on the fully exploded BOM of matching Items to the results<br> |

The Header option determines if custom attributes appear  by their API name or their actual name within the header of the exported CSV files.


| header<br> | Description<br> |
|  --- |  --- | 
| apiName<br> | The apiName is the GUID for the Item, BOM, Supplier and Supplier Item custom attribute. Example: "DVFYHPYYVCTBUDWDIYP0". API name is the default setting if not specified.<br> |
| name<br> | The name is the name of the custom attribute as it appears in the Workspace Settings of the graphic user interface. Example: "Capacitance".<br> |

Item Revision Status


| revisionStatus<br> | Description<br> |
|  --- |  --- | 
| LATEST<br> | Returns the effective revision of the items matching the criteria if the Item is effective, otherwise returns the working revision of the Items matching the criteria. For BOMs, returns the latest revisions for all levels.<br> |
| WORKING<br> | Returns the working revisions of the Items matching the criteria, even if the Item is effective. For BOMs, returns the working revision of the parent Item, but returns the latest revision for all other levels.<br> |
| POTENTIAL<br> | Returns the working revisions of the Items matching the criteria, even if the Item is effective. For BOMs, returns the working revision for all levels, including the parent Item.<br> |

API Export Format


| format<br> | Description<br> |
|  --- |  --- | 
| json<br> | Returns the export data in JSON file format. If Files are included the JSON file format is included with the Files in a zip file.<br> |
| csv<br> | Returns the export data in CSV file format. If Files are included the CSV file format is included with the Files in a zip file.<br> |

