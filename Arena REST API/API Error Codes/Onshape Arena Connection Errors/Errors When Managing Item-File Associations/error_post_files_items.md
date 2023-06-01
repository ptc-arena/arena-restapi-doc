# Errors When Adding Files to an Item
POST /items/&lt;GUID&gt;/files

This endpoint is used to add a file to an Item through the Items World.  The file object still will be created and will be accessible through the Files World. This endpoint requires that the Authorize User must have a Full License, Item Read & Write and File Read & Edit Access Policy Rules in Arena.


| Status Code<br> | Error Code<br> | Message<br> | Explanation<br> |
|  --- |  --- |  --- |  --- | 
| 400<br> | 3024<br> |  ```Either you do not have privileges to access the requested data or it does not exist.```  | The Onshape-Arena User may not have the following:<br> <br> * A Full license.<br><br> * Item Read & Write Access Policy Rules.<br><br> * File Read & Write Access Policy Rules<br><br> * Prohibited Based On Category, Procurement Type, Lifecycle Phases.<br>Arena: The user can attempt to add a file to the same type of item in Arena to see if they have the required permissions.<br>Otherwise, the Arena Administrator can check the user access policies.<br> |
| 400<br> | 3011<br> |  ```The guid “{0}” is not valid.```  | The file category being assigned to the File does not exist in Arena. The file category could have been removed.<br>The user can attempt to create a file with the same File Category in Arena to see if the File Category is valid.<br>Otherwise, the Arena Administrator can check the File Categories.<br>Example: The guid \"J1L49Y1KSGZ9SBNUN5OX\" is not valid.<br>\{0\} = File Category GUID.<br> |
| 400<br> | 3001<br> |  ```The attribute “{0}” is required.```  | All files require a Title.<br>Example: The attribute \"title\" is required.<br>\{0\} - Title.<br> |
| 400<br> | 3033<br> |  ```The file content is missing.```  | The file being referenced does not exist and therefore cannot be uploaded. The file could have been deleted from the source location or is not ready to be uploaded.<br> |
| 400<br> | 3034<br> |  ```The item is locked.```  | The working revision of the unreleased item is assigned to a submitted change so the file cannot be added to the item.<br>Lock icons will appear within the Files view of the item.<br> |
| 400<br> | 3066<br> |  ```The working revision of the item is locked by inclusion in at least one change. ```  | The working revision of the Item has been assigned to a Change that is submitted for approval or has been approved and is waiting to be made effective.<br>Viewing the Item in Arena you will see locks on the Item &gt; Files section.<br> |

