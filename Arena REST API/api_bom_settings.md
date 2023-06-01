# BOM and Workspace Settings
When constructing requests to the Arena REST API, it’s important to understand how settings in the target Arena workspace can affect how the request is handled. This is particularly true for requests to create or update BOM Lines.

BOM Settings are set per BOM in the BOM view of an Item in Arena; workspace settings are workspace-wide and are set in the Account Administration tool of Arena. If settings are not specified for a BOM, the BOM uses the workspace settings.


| Setting<br> | Type<br> |   |
|  --- |  --- |  --- | 
| Reference Designator Checking<br> | BOM Setting<br> | When this is set to ON for a BOM, Arena enforces that:<br> <br> * the quantity for a row must match the number of references designators specified.<br><br> * duplicate reference designators are not allowed. When set to OFF for a BOM, no check is performed.<br>When set to OFF for a BOM, no check is performed.<br> |
| Automatic Line Number Generation<br> | BOM Setting<br> | When this is set to ON for a BOM, Items added to the BOM are sorted by Item Number, and a line number is assigned automatically. When set to OFF for a BOM, you can specify a persistent line number for each BOM Item.<br> |
| Reference Designator Checking for New Assemblies<br> | Workspace Setting<br> | When this is set to ON for a workspace, Arena enforces the following when creating a new assembly:<br> <br> * the quantity for a row must match the number of references designators specified.<br><br> * duplicate reference designators are not allowed.<br>When set to OFF for a workspace, no check is performed when creating a new assembly.<br> |
| Negative Quantities Allowed<br> | Workspace Setting<br> | When this is set to YES for a workspace, you can specify a negative quantity for a BOM Line. When set to NO for a workspace, negative quantities will result in an error.<br> |

