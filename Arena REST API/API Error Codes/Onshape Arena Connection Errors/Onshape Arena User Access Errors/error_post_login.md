# Errors Encountered When Logging In
POST /login

This endpoint is used to establish an initial connection between Onshape & Arena through an Arena Full Licensed Employee that has a WebToken assigned. This endpoint will be used to authorize the Onshape User via POST /login/authorizeuser. If neither endpoint is successful then the Onshape Arena Settings \(Onshape &gt; Settings &gt; Arena\) will be incomplete and the Mappings will not be able to be refreshed & the Synchronization Process will fail


| Status Code<br> | Error Code<br> | Message<br> | Explanation<br> |
|  --- |  --- |  --- |  --- | 
| 503<br> | 503<br> |  ```The service is currently unavailable.``` | The service is currently unavailable.<br> |
| 400<br> | 4079<br> |  ```API feature is not enabled for your workspace.``` | Workspace does not have the API Feature enabled.<br>Please contact Arena Support to enable the feature.<br> |
| 400<br> | 4090<br> |  ```The Onshape feature is not enabled in your workspace.``` | Workspace does not have the Onshape Integration Feature enabled. Without this a webtoken cannot be assigned to the Full License Standard Employee.<br>Please contact Arena Support to enable the feature and setup a webtoken for the Full License Standard Employee used by the POST /login API endpoint.<br> |
| 400<br> | 4089<br> |  ```Invalid Token.``` | Invalid Webtoken for Workspace: The webtoken is invalid or has been updated for the target workspace or the incorrect workspace is being referenced.<br>Employee Assigned WebToken has For Integration Use disabled: Update the Employee &gt; For Integration Use = Yes under the Arena &gt; Workspace &gt; Settings &gt; Employees &gt; Employee.<br> |
| 400<br> | 4001<br> |  ```The username, password or workspace ID is not valid or you are not allowed to log in due to IP restriction.``` | Employee Assigned WebToken has been disabled. Arena Administrator can enable user under the Arena &gt; Workspace &gt; Settings &gt; Employees &gt; Employee.<br>Employee Assigned WebToken has not logged into Arena for the first time to set their Arena password: All Standard Users created are required to log into the Arena Application after being created and update their password. The Arena Administrator can assist with this action item.<br> |
| 400<br> | 4083<br> |  ```Too many invalid password attempts, account disabled for five minutes.``` | Employee Assigned WebToken has attempted to log into Arena multiple time and the failures resulted in the account becoming locked for a specific time. Wait for the time to elapse and start the process again.<br>Employee Assigned WebToken should be a dedicated non\-daily User Assigned Full License with WebToken.<br> |

