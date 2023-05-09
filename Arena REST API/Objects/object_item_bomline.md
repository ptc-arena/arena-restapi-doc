# Item BOM Line

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| additionalAttributes | Array of additional Attributes | The additional attributes of a BOM line. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute. |
| guid | Reference | The unique identifier for the BOM Line. |
| item | Reference | The child item. Contains the attributes creationDateTime and guid. |
| lineNumber | Integer | The BOM line number of a child item |
| notes | String | The BOM Notes of a child item |
| refDes | String | The reference designator values of a child item |
| quantity | Integer | The quantity of a child item |
| url | Array of References | The direct urls of the object within the api and the application. |

