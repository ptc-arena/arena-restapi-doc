# Login

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| loginDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a user's session began |
| logoutDateTime | Date\-Formatted String | the date and time \(in Zulu format\) a user's session ended \(null for currently logged in\) |
| duration | Integer | The length in minutes of a session \(null for currently logged in\) |
| connectedThrough | String | The application Zone through which the user connected to Arena. Values can be Arena; Arena FileDrop; SmartLink; Arena PartsList; Arena REST API; Arena Exchange; N/A |
| originatingIP | String | The IP from which the user connected to Arena |
| domain | String | The domain from which the user connected to Arena \(null for unknown\) |
| user | Reference | The user logging in. See  object. |

