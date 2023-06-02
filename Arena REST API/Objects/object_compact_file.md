# File Compact

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| category  | reference  | The category to which a file is assigned. Contains a category GUID.  |
| corrected  | boolean  | Indicates whether a File has been corrected or not. True if corrected. False if not.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) \(in Zulu time\) at which a file edition was created  |
| edition  | String  | The edition identifier of a file  |
| format  | String  | The format of a file  |
| guid  | String  | The unique identifier for a file  |
| name  | String  | The name of a file. This attribute cannot be edited and is set by Arena. When uploading file content \(creating a File or File Edition with storageMethodName "FILE"\), Arena derives the name from the content. For Files without content \(a FIle with storageMethodName "WEB", "FTP", or "PLACE_HOLDER"\), the value is null.  |
| number  | String  | The number of a file  |
| title  | String  | The title of a file  |

