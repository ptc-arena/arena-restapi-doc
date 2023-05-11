# Login

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| loginDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a user's session began<br> |
| logoutDateTime<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a user's session ended \(null for currently logged in\)<br> |
| duration<br> | Integer<br> | The length in minutes of a session \(null for currently logged in\)<br> |
| connectedThrough<br> | String<br> | The application Zone through which the user connected to Arena. Values can be Arena; Arena FileDrop; SmartLink; Arena PartsList; Arena REST API; Arena Exchange; N/A<br> |
| originatingIP<br> | String<br> | The IP from which the user connected to Arena<br> |
| domain<br> | String<br> | The domain from which the user connected to Arena \(null for unknown\)<br> |
| user<br> | Reference<br> | The user logging in. See object.<br>Compact User<br> |

