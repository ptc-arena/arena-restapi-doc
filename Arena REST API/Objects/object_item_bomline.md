# Item BOM Line

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| additionalAttributes<br> | Array of additional Attributes<br> | The additional attributes of a BOM line. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute.<br> |
| guid<br> | Reference<br> | The unique identifier for the BOM Line.<br> |
| item<br> | Reference<br> | The child item. Contains the attributes creationDateTime and guid.<br> |
| lineNumber<br> | Integer<br> | The BOM line number of a child item<br> |
| notes<br> | String<br> | The BOM Notes of a child item<br> |
| refDes<br> | String<br> | The reference designator values of a child item<br> |
| quantity<br> | Integer<br> | The quantity of a child item<br> |
| url<br> | Array of References<br> | The direct urls of the object within the api and the application.<br> |

