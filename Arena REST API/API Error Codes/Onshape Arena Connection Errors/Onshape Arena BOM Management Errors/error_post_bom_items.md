# Errors When Adding and Updating a BOM
POST /items/&lt;GUID&gt;/BOM

PUT /items/&lt;GUID&gt;/BOM/&lt;GUID&gt;

These endpoints are used to create or update an item’s bill of materials with bom additional attributes. These endpoints require that the Authorize User must have a Full License, Item Read & Write and File Read & Edit Access Policy Rules in Arena. This endpoint will return the following error information under the following scenarios:  


| Status Code | Error Code | Message | Explanation |
|  --- |  --- |  --- |  --- | 
| 400 | 3230 |   | The BOM Item Reference Designator Information Count does not match the Quantity.  |
| 400 | 3227 |   | The BOM Item Quantity is assigned a negative value when negative quantities are not allowed. |
| 400 | 3235 |   | The Item already exists on the BOM and duplicates are not allowed. |
| 400 | 3229 |   | The Reference Designator Information is already assigned on the BOM to another BOM Item when duplicate Refdes information is not allowed. |
| 400 | 3232 |   | The line number is being assigned a value when the system is setup to automatically generate line numbers. |
| 400 | 2014 |   | The BOM Attribute being updated with an empty value. |
| 400 | 2002 |   | The BOM Attribute being updated is being assigned an invalid value \(i.e. OnshapeCreated allows Yes or No but the system passes something different. |
| 400 | 3037 |   | The BOM Item being added already appears at a higher level in the bom structure. This will result in recursive reference. Simple example is attempting to add an Item to it’s own Bill of Materials. |
| 400 | 3237 |   | The working revision of the Item has been assigned to a Change that is submitted for approval or has been approved and is waiting to be made effective. |
| 400 | 3233 |   | BOM notes cannot exceed 4000 characters. |
| 400 | 3606 |   | Reference designators can only be entered as a letter and a number pair separated by commas. A range of reference designators can be indicated by a dash. |

```
Quantity ({0}) does not match number of reference designators specified for the BOM line.
```
Example: Quantity \(3\) does not match number of reference designators specified for the BOM line. 

Dependent: This error is dependent on the Arena &gt; Workspace Settings &gt;  Summary &gt; Settings \- Reference Designator Checking for New Assemblies = Check. 

\{0\} \- BOM Item Quantity.

```
Quantity must be positive.
```
Example: Quantity \(\-1\) does not match number of reference designators specified for the BOM line.

Dependent: This error is dependent on the Arena &gt; Workspace Settings &gt;  Summary &gt; Settings \- Negative Quantities Allowed = No

\{0\} \- BOM Item Quantity

```
Cannot add duplicate item "{0}"“{1}”.
```
Example: Cannot add duplicate item \"VDXGLADW4SBJ2GY3EITQ\" \”100\-0001\”.

Dependent: This error is dependent on the Arena &gt; Workspace Settings &gt;  Summary &gt; Settings \- Identical BOM Items Allowed = No

\{0\} \- Item GUID

\{1\} \- Item Number or Item Name.

```
Reference designator "{0}" is already defined in BOM Line: {1}.
```
Example: Reference designator \"\[R6, R7\]\" is already defined in BOM Line: N5P8D25OWK3ATC1ZJM6C.

Dependent: This error is dependent on the Arena &gt; Workspace Settings &gt;  Summary &gt; Settings \- Reference Designator Checking for New Assemblies = Check. 

\{0\} \- Duplicate Reference Designator 

\{1\} \- BOM Item Number GUID.

```
The attribute "{0}" is not editable for this BOM.
```
The attribute \"lineNumber\" is not editable for this BOM.

Dependent: This error is dependent on the Arena &gt; Workspace Settings &gt;  Summary &gt; Settings \- Line Numbering Method for New Assemblies = Automatically Generate.

\{0\} \- Line Number.

```
Empty or blank is not a valid option for additional attribute "{0}"“{1}”.
```
Example: Empty or blank is not a valid option for additional attribute \"Q8SBG58RZN4M5O7Q9QTV\" \”OnShapeCreated\”.

Make sure that the BOM Attribute has a value list that contains all possible allowed values \(i.e. Yes, No\)

\{0\} \- BOM Attribute GUID.

\{1\} \- BOM Attribute Name.

```
The specified value "{0}" is not a valid option for additional attribute "{1}".
```
Example: The specified value \"TBD\" is not a valid option for additional attribute \"OnshapeCreated\".

Make sure that the BOM Attribute has a value list that contains all possible allowed values \(i.e. Yes, No\)

\{0\} \- Assigned Value.

\{1\} \- BOM Attribute Name.

```
The item "{0}"“{1}” appears at a higher level in the fully indented BOM and cannot be added at this level.
```
Example: The item \"5N7QVKN6E2LTCQ8DOIV3\" \”100\-0001\” appears at a higher level in the fully indented BOM and cannot be added at this level.

\{0\} \- Item GUID.

\{1\} \- Item Number.

```
An item can only be added to the working revision BOM. Effective BOMs are locked from editing.
```
Viewing the Item in Arena you will see locks on the Item &gt; Bill of Materials section. 

An item can only be added to the working revision BOM. Effective BOMs are locked from editing.

```
Notes must be smaller than 4000.
```
```
Invalid reference designator: “{0}” Reference designators must be entered as a comma separated list using format [letter][number] or [letter][number]-[letter][number] for a range. Ex: R1,R2,R4-R10.
```
\{0\} \- Invalid Reference Designator Being Assigned

