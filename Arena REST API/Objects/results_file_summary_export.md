# Export Results: File Summary 
File Summary attributes are listed in the order that they appear in the CSV file..


| Field | Data Type | Description |
|  --- |  --- |  --- | 
| name | String | The name of the File. |
| location | String | When storageMethodName is WEB or FTP, the value is the url of a file. When storageMethodName is FILE or PLACE_HOLDER, the value is always null and cannot be included in requests. |
| number | String | The number of the File. |
| edition | String | The edition identifier of a File. |
| title | String | The title of a File. |
| storageMethodName | String | Indicates where or not a file is stored on the Arena servers. The value can be FILE \(stored on Arena servers\), PLACE_HOLDER \(placeholder for later upload\), FTP \(stored on user FTP server\), WEB \(web link\). |
|  category | Reference | The category of the File. Includes guid, name, and path. |
| guid | String | The unique id of the File Summary |
| description | String | The description of the File. |
| author.fullName | String | The author of a File. |
| format | String | The format of a File. |
| size | Integer | The size of a File. |
| creationDateTime | Date\-Formatted String | The date and time \(in Zulu format\) the File was created. |
| lastModifiedDataTime | Date\-Formatted String | The date and time \(in Zulu format\) a File was modified. |
| hasMarkup | Boolean | Indicates if a File has markups. Value can be true or false. |
| mimeType | String | Identifier for file formats and format contents transmitted on the Internet |
| private | Boolean | Indicates if a File is private. Value can be true or false. |
| latest | Boolean | Indicates if a File is the latest edition. Value can be true or false. |
| locked | Boolean | Indicates if a File is locked. Value can be true or false. |
| contentPath | String | Directory structure path to the location of the physical file in the export zip file. |

