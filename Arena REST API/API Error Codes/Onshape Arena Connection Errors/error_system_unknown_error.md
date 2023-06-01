# Unknown Errors and System Errors
All Endpoints.

These process level errors can occur at any point in-time within the Onshape Arena Integration. These errors will return the following response error message structure elements when it’s unknown on why the error was encountered.


| Status Code<br> | Error Code<br> | Message<br> | Explanation<br> |
|  --- |  --- |  --- |  --- | 
|   | 3000<br> |  ```Sorry, a system error occurred, please try again.```  | The item being deleted no longer exists on the BOM.<br>Contact Arena Support with the Date/Time of Incident, Events Leading Up to the Error as well as the Number of Occurrences.<br> |
| 400<br> | 4087<br> |  ```Unknown errors encountered. Please contact Arena Technical Support{0}.```  | Contact Arena Support with the Date/Time of Incident, Events Leading Up to the Error as well as the Number of Occurrences.<br>\{0\} Support Code.<br> |

