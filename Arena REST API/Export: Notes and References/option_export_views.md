# Export Options
Export options determine what Item views and attributes are included in an export.

Export Views table displays which views of an Item can be included in an export.


| exportViews | Description |
|  --- |  --- | 
| SPECS | Specs data for all Items. |
| BOM | BOM Lines for all Items |
| BOM_SUBSTITUTES | BOM Substitutes for all Items |
| SOURCING | Sourcing relationships for all Items |
| FILES | File Associations for all Items |
| FILES_FILE_SUMMARY | File summary for all Files on Item Files |
| SOURCING_SUPPLIERITEM_SPECS | Supplier Item Specs for all Supplier Items on Item sourcing |
| SOURCING_SUPPLIERITEM_SUPPLIER_PROFILE | Supplier Profile for all Supplier Items on Item sourcing |
| SOURCING_SUPPLIERITEM_FILES | Supplier Item File associations for all Supplier Items in Sourcing |
| SOURCING_SUPPLIERITEM_FILES_FILE_SUMMARY | File summary for all files on Supplier Items on Item Sourcing |

File Content determines if the actual Files associated with Items and Supplier Items are included within the export. Assigning a value of PRIMARY to fileContent is not supported for supplierItem.


| fileContent | Description |
|  --- |  --- | 
| NONE | Export does not include any physical files. Can be used for Items and Supplier Items. |
| PRIMARY | Export includes only the Primary physical Files. Can be used ONLY for Items. |
| ALL | Export includes all Files. Can be used for Items and Supplier Items. |

BOM Levels adds children Items on the BOM of matching Items to the results.


| bomLevels | Description |
|  --- |  --- | 
| NONE | Does not add child Items to the results |
| SINGLE | Adds the Items on the single level BOM of matching Items to the results |
| FULL | Add s the Items on the fully exploded BOM of matching Items to the results |

The Header option determines if custom attributes appear  by their API name or their actual name within the header of the exported CSV files.


| header | Description |
|  --- |  --- | 
| apiName | The apiName is the GUID for the Item, BOM, Supplier and Supplier Item custom attribute. Example: "DVFYHPYYVCTBUDWDIYP0". API name is the default setting if not specified. |
| name | The name is the name of the custom attribute as it appears in the Workspace Settings of the graphic user interface. Example: "Capacitance". |

Item Revision Status


| revisionStatus | Description |
|  --- |  --- | 
| LATEST | Returns the effective revision of the items matching the criteria if the Item is effective, otherwise returns the working revision of the Items matching the criteria. For BOMs, returns the latest revisions for all levels. |
| WORKING | Returns the working revisions of the Items matching the criteria, even if the Item is effective. For BOMs, returns the working revision of the parent Item, but returns the latest revision for all other levels. |
| POTENTIAL | Returns the working revisions of the Items matching the criteria, even if the Item is effective. For BOMs, returns the working revision for all levels, including the parent Item. |

API Export Format


| format | Description |
|  --- |  --- | 
| json | Returns the export data in JSON file format. If Files are included the JSON file format is included with the Files in a zip file. |
| csv | Returns the export data in CSV file format. If Files are included the CSV file format is included with the Files in a zip file. |

