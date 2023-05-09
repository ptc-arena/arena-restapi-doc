# Import Engine Source File
The Import Engine supports a single resource per import run. The source file contains data for that resource.

The following source file formats are supported:

* Microsoft 2007 Excel XLSX worksheet

* Comma Separated Values \(CSV\) adhering to RFC\-4180 encoded in UTF\-8.

Each column within the source file represent an attribute.

Each row within the source file represents a resource.

As of our Spring 2023 release, the Import Engine supports two resources: ITEM_SPECS and ITEM_BOM. These two resources are equivalent to the Specs view and BOM view of an Item respectively.

