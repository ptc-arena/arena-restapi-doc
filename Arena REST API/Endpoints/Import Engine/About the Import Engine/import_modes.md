# Import Engine Modes
The table below lists the Import Engine Modes, the supported options for each mode, and a brief description of the mode.


| Import Engine Mode | Supported Import Options | Description |
|  --- |  --- |  --- | 
| CREATE | createDuplicates<br>multiSelectDelimiter<br>checkRefDes<br>timeZone<br>addToChange<br>stripWhiteSpace<br>numberingFreeTextHeader | Import definitions with the CREATE mode are intended to create new resources that currently do not exist. Required attributes must either be provided in the source file or have default values. |
| EDIT | matchDuplicates<br>matchDuplicateParents<br>removeValue<br>multiSelectDelimiter<br>checkRefDes<br>timeZone<br>addToChange<br>stripWhiteSpace<br>numberingFreeTextHeader | EDIT mode imports are intended to edit an existing resource. If the GUID is present in the source file, it is used first. If the GUID is not present, key attributes are required. |
| OVERWRITE | matchDuplicates<br>removeValue<br>multiSelectDelimiter<br>checkRefDes<br>timeZone<br>addToChange<br>stripWhiteSpace<br>numberingFreeTextHeader | OVERWRITE mode edits existing resources and creates new resources if the resource within the source file does not exist. |
| REPLACE | matchDuplicateParents<br>multiSelectDelimiter<br>checkRefDes<br>timeZone<br>addToChange<br>stripWhiteSpace | REPLACE mode replaces the entire view of the parent resource with the contents of the source file. Currently this can only be used with the ITEM_BOM resource. |
| DELETE | matchDuplicates<br>stripWhiteSpace | DELETE mode deletes the existing data. |

