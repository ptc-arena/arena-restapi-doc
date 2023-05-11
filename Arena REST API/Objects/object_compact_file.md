# File Compact

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| category<br> | reference<br> | The category to which a file is assigned. Contains a category GUID.<br> |
| corrected<br> | boolean<br> | Indicates whether a File has been corrected or not. True if corrected. False if not.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) \(in Zulu time\) at which a file edition was created<br> |
| edition<br> | String<br> | The edition identifier of a file<br> |
| format<br> | String<br> | The format of a file<br> |
| guid<br> | String<br> | The unique identifier for a file<br> |
| name<br> | String<br> | The name of a file. This attribute cannot be edited and is set by Arena. When uploading file content \(creating a File or File Edition with storageMethodName "FILE"\), Arena derives the name from the content. For Files without content \(a FIle with storageMethodName "WEB", "FTP", or "PLACE_HOLDER"\), the value is null.<br> |
| number<br> | String<br> | The number of a file<br> |
| title<br> | String<br> | The title of a file<br> |

