# Errors Encountered When Reserving Item Numbers for Onshape
POST /settings/items/numberreservations/onshape

This endpoint is used to reserve Onshape Item Numbers in Arena where the Onshape Part has been assigned an Item Category.  This can be performed on an individual part or on multiple parts listed on an Onshape BOM \(bulk\). This endpoint performs a Login using the Employee WebToken User, Reserves the Item & Logs out. The POST /login & POST /login/authorizeuser endpoints are not a pre\-requisite prior to it’s execution.


| Status Code | Error Code | Message | Explanation |
|  --- |  --- |  --- |  --- | 
| 400 | 3024 |   | The Employee WebToken User is NOT assigned a Full License.    |
| 400 | 3011 |   | The Onshape Category is mapped to an Arena Item Category that does not exist in Arena. Check the Onshape &gt; Settings &gt; Arena \- Mappings & the Arena &gt; Settings &gt; Categories &gt; Items.  |
| 400 | 3238 |   | The Onshape Category is mapped to an Arena Item Category that was was deleted by the Arena Administrator. The Category cannot be restored. It has to be re\-created and the Onshape Arena Mapping must be updated. Even though they have the same name they will have different GUIDs. |
| 400 | 3038 |   | The Onshape Category is mapped to an Arena Item Category that is inactive. The Category can be re\-activated by the Arena Administrator. Once active, the Onshape Arena Part Number Reservation should work as expected. |
| 400 | 3214 |   | The Onshape Category is mapped to an Arena Item Category that is not assigned a number format. The Category should be edited and a Number Format should be assigned by the Arena Administrator.  |
| 400 | 3110 |   | The Onshape Category is mapped to an Arena Item Category that is associated with a number format without an auto increment field.  |
| 400 | 3295 |   | The value within X\-Web\-Token, X\-Workspace\-ID, or X\-Item\-Number\-Reservation\-ID is not valid. |

```
Either you do not have privileges to access the requested data or it does not exist.
```
Arena Administrator can update the user’s license requirement as long as there is a license available. 

```
Arena Administrator can update the user’s license requirement as long as there is a license available.
```
\{0\} represents the GUID being referenced by Onshape. Since it does not exist in Arena a Category Name cannot be provided.

```
The category "{1}" (guid {0}) is deleted.
```
\{0\} represents the Category GUID.

\{1\} represents the Arena Category Name

```
The category "{1}" (guid {0}) is inactive.
```
\{0\} represents the Category GUID.

\{1\} represents the Arena Category Name.

```
The category guid ”{0}” ”{1}” does not have a number format.
```
Numbers cannot be reserved if the Item Category does not have a number format assigned.

\{0\} represents the Category GUID.

\{1\} represents the Arena Category Name.

```
The category guid “{0}”{1}” without auto sequencing number format value is not allowed to reserve number.
```
Numbers cannot be reserved if the number format does not include an auto increment field. 

\{0\} represents the Category GUID.

\{1\} represents the Arena Category Name.

```
The request header {0} is not valid.
```
