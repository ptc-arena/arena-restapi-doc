# Export Results: File Summary 
File Summary attributes are listed in the order that they appear in the CSV file..


| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | String<br> | The name of the File.<br> |
| location<br> | String<br> | When storageMethodName is WEB or FTP, the value is the url of a file. When storageMethodName is FILE or PLACE_HOLDER, the value is always null and cannot be included in requests.<br> |
| number<br> | String<br> | The number of the File.<br> |
| edition<br> | String<br> | The edition identifier of a File.<br> |
| title<br> | String<br> | The title of a File.<br> |
| storageMethodName<br> | String<br> | Indicates where or not a file is stored on the Arena servers. The value can be FILE \(stored on Arena servers\), PLACE_HOLDER \(placeholder for later upload\), FTP \(stored on user FTP server\), WEB \(web link\).<br> |
| category<br> | Reference<br> | The category of the File. Includes guid, name, and path.<br> |
| guid<br> | String<br> | The unique id of the File Summary<br> |
| description<br> | String<br> | The description of the File.<br> |
| author.fullName<br> | String<br> | The author of a File.<br> |
| format<br> | String<br> | The format of a File.<br> |
| size<br> | Integer<br> | The size of a File.<br> |
| creationDateTime<br> | Date-Formatted String<br> | The date and time \(in Zulu format\) the File was created.<br> |
| lastModifiedDataTime<br> | Date-Formatted String<br> | The date and time \(in Zulu format\) a File was modified.<br> |
| hasMarkup<br> | Boolean<br> | Indicates if a File has markups. Value can be true or false.<br> |
| mimeType<br> | String<br> | Identifier for file formats and format contents transmitted on the Internet<br> |
| private<br> | Boolean<br> | Indicates if a File is private. Value can be true or false.<br> |
| latest<br> | Boolean<br> | Indicates if a File is the latest edition. Value can be true or false.<br> |
| locked<br> | Boolean<br> | Indicates if a File is locked. Value can be true or false.<br> |
| contentPath<br> | String<br> | Directory structure path to the location of the physical file in the export zip file.<br> |

