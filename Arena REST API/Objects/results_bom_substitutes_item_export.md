# Export Results: Item BOM Substitutes
BOM Substitutes attributes are listed in the order they appear in the BOM Substitutes CSV file.


| Field | Data Type | Description |
|  --- |  --- |  --- | 
| parent | Reference | Parent Item. Includes number, guid, revisionNumber, and name. |
| item | Reference | Child Item Number. Includes number, guid, revisionNumber, and name. |
| substitute | Reference | Substitute Child Item. Includes number, guid, revisionNumber, and name. |
| bom.guid | String | GUID of the BOM being substituted |
| guid | String | The unique identifier of the BOM substitute. |
| rank | Integer | The rank of the substitute |
| quantity | Integer | The quantity of the substitute. |
| notes | String | BOM Substitute notes |

