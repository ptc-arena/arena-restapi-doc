# Errors When Removing an Item From a BOM
DELETE /items/&lt;GUID&gt;/bom/&lt;GUID&gt;

This endpoint is used to remove an existing BOM Item from an Item’s Bill of Materials.  This endpoint require that the Authorize User must have a Full License, Item Read & Write and File Read & Edit Access Policy Rules in Arena. This endpoint will return the following error information under the following scenarios:


| Status Code  | Error Code  | Message  | Explanation  |
|  --- |  --- |  --- |  --- | 
| 400  | 3012  |  ```The requested object with guid “{0}” is not found.```    | The item being deleted no longer exists on the BOM.Example: The requested object with guid \"Q8SBG58RZN6DWF42MP9J\" is not found.<br> Check the BOM in Arena to see if the BOM Item was removed recently.<br> \{0\} -BOM  Item GUID.<br>   |
| 400  | 3034  |  ```Item is locked.```    | An item can only be removed from the working revision BOM. Effective BOMs are locked from editing.Viewing the Item in Arena you will see locks on the Item &gt; Bill of Materials section. <br>   |

