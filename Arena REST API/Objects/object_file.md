# File

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| author  | Reference  | The author of a file. Contains the attribute fullName.  |
| category  | Reference  | Details of the category to which the file is assigned. See Category object.  |
| corrected  | Boolean  | Indicates whether a File has been corrected or not. True if corrected. False if not.  |
| creationDateTime  | Date-Formatted String  | The date and time \(in Zulu format\) a file was created  |
| description  | String  | The description of a file  |
| edition  | String  | The edition identifier of a file  |
| format  | String  | The format of a file \(e.g. PDF, docx\)  |
| guid  | String  | The unique identifier for a file  |
| hasMarkup  | Boolean  | Indicates whether or not a file has a markup.  |
| lastModified DateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a file was modified  |
| latest  | Boolean  | Indicates whether or not a file is the latest edition. The value can be true or false.  |
| location  | String  | When storageMethodName is WEB or FTP, the url of a file. When storageMethodName is FILE or PLACE_HOLDER, the value is always null and cannot be included in requests.  |
| locked  | Boolean  | Indicates if a file edition is locked to edits. The value can be true \(locked\) or false \(not locked\).  |
| mimeType  | String  | The mime type of a file.  |
| name  | String  | The name of a file. This attribute cannot be edited and is set by Arena. When uploading file content \(creating a File or File Edition with storageMethodName "FILE"\), Arena derives the name from the content. For Files without content \(a FIle with storageMethodName "WEB", "FTP", or "PLACE_HOLDER"\), the value is null.  |
| number  | String  | The number of a file  |
| private  | Boolean  | Indicates if a file is hidden from all Supplier users. The value can be true \(private\) or false \(public\).  |
| size  | Long  | The size of a file  |
| storageMethod\*   | Integer  | **DEPRECATED - Please use storageMethodName.** Indicates whether or not a file is stored on the Arena servers. The value can be - 0 \(uploaded\), 1 \(place holder\), 2 \(ftp link\), 3 \(web link\).  |
| storageMethodName  | String  | Indicates whether or not a file is stored on the Arena servers. The value can be FILE \(stored on Arena servers\), PLACE_HOLDER \(placeholder for later upload\), FTP \(stored on user FTP server\), WEB \(web link\).  |
| title  | String  | The title of a file  |

