# File

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| author<br> | Reference<br> | The author of a file. Contains the attribute fullName.<br> |
| category<br> | Reference<br> | Details of the category to which the file is assigned. See object.<br>Category<br> |
| corrected<br> | Boolean<br> | Indicates whether a File has been corrected or not. True if corrected. False if not.<br> |
| creationDateTime<br> | Date\-Formatted String<br> | The date and time \(in Zulu format\) a file was created<br> |
| description<br> | String<br> | The description of a file<br> |
| edition<br> | String<br> | The edition identifier of a file<br> |
| format<br> | String<br> | The format of a file \(e.g. PDF, docx\)<br> |
| guid<br> | String<br> | The unique identifier for a file<br> |
| hasMarkup<br> | Boolean<br> | Indicates whether or not a file has a markup.<br> |
| lastModified DateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a file was modified<br> |
| latest<br> | Boolean<br> | Indicates whether or not a file is the latest edition. The value can be true or false.<br> |
| location<br> | String<br> | When storageMethodName is WEB or FTP, the url of a file. When storageMethodName is FILE or PLACE_HOLDER, the value is always null and cannot be included in requests.<br> |
| locked<br> | Boolean<br> | Indicates if a file edition is locked to edits. The value can be true \(locked\) or false \(not locked\).<br> |
| mimeType<br> | String<br> | The mime type of a file.<br> |
| name<br> | String<br> | The name of a file. This attribute cannot be edited and is set by Arena. When uploading file content \(creating a File or File Edition with storageMethodName "FILE"\), Arena derives the name from the content. For Files without content \(a FIle with storageMethodName "WEB", "FTP", or "PLACE_HOLDER"\), the value is null.<br> |
| number<br> | String<br> | The number of a file<br> |
| private<br> | Boolean<br> | Indicates if a file is hidden from all Supplier users. The value can be true \(private\) or false \(public\).<br> |
| size<br> | Long<br> | The size of a file<br> |
| storageMethod\*<br> | Integer<br> | Indicates whether or not a file is stored on the Arena servers. The value can be \- 0 \(uploaded\), 1 \(place holder\), 2 \(ftp link\), 3 \(web link\).<br>DEPRECATED \- Please use storageMethodName.<br> |
| storageMethodName<br> | String<br> | Indicates whether or not a file is stored on the Arena servers. The value can be FILE \(stored on Arena servers\), PLACE_HOLDER \(placeholder for later upload\), FTP \(stored on user FTP server\), WEB \(web link\).<br> |
| title<br> | String<br> | The title of a file<br> |

