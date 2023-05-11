# Errors Encountered When Authorizing an Onshape User
POST /login/authorizeuser

This endpoint is used to authorize the Onshape User with Arena after a session has been established by the POST /login endpoint. If this endpoint cannot establish a session then the Onshape Arena Settings \(Onshape &gt; Settings &gt; Arena\)  will be incomplete and the Mappings will not be able to be refreshed. In addition, the user will not be able to sync Onshape with Arena.


| Status Code<br> | Error Code<br> | Message<br> | Explanation<br> |
|  --- |  --- |  --- |  --- | 
| 400<br> | 4081<br> |  ```Your password has either been reset by an Account Administrator or has expired. Please proceed to the browser-based Arena user interface and configure a new password.``` | Error occurs when Onshape\-Arena Employee User encounters the following scenarios:  <br> <br> * Not performed an initial Arena Login.<br><br> * Password has Expired<br><br> * Password Reset by Arena Administrator<br>The solutions for each issue are listed below:<br> <br> * All Onshape Arena Employee Users are required to log into the Arena Application after being created to update their password.<br><br> * Reset your expired password in Arena.<br><br> * Check with the Arena Admin on the resetting of the passwords<br> |
| 400<br> | 4083<br> |  ```Too many invalid password attempts, account disabled for five minutes.``` | The Onshape Arena Employee User has failed to login successfully and the account has been locked for 5 minutes.<br>Wait for the lockout time to elapse and try process again.<br>Note: Don’t share accounts & Reset your password periodically.<br> |
| 400<br> | 20001<br> |  ```Insufficient privileges for this user.``` | Onshape Arena Employee User that is being authorized has been disabled. Arena Administrator can enable user under the Arena &gt; Workspace &gt; Settings &gt; Employees &gt; Employee.<br>Onshape Arena Employee User that is being authorized has not logged into Arena for the first time to set their Arena password: All Standard Users created are required to log into the Arena Application after being created and update their password. The Arena Administrator can assist with this action item.<br> |
| 500<br> | 20000<br> |  ```User not authenticated.``` | A login session could not be established through the POST /login endpoint. Arena Administrator can check both the Arena Employee User assigned the WebToken and the Authorize User to make they are configured correctly.<br> |
| 400<br> | 20016<br> |  ```User not authorized for workspace.``` | Onshape Arena Employee User that is being authorized does not have access to the target workspace. Arena Administrator can grant the user access to the workspace with a Full License and the required access policies.<br>The login session established through the POST /login endpoint has expired. Restart the process because the POST /login must be re\-executed to establish a new session.<br>Note: Onshape users that are created as new Full Licensed Employees in Arena are assigned to the Arena Workspace that is being referenced by Onshape. As well as assigned the required access polices.<br> |
| 400<br> | 20015<br> |  ```User email address not found.``` | The Onshape Arena User Email does not exist in Arena. Arena Administrator can add the Onshape User as an Arena Full Licensed Employee with the required Access Policies<br>Note: Each Onshape User that is synchronizing to Arena should be created in Arena as a Full License Standard Employee with at least Item & File Read & Edit Policies.<br> |

* Not performed an initial Arena Login.

* Password has Expired

* Password Reset by Arena Administrator

* All Onshape Arena Employee Users are required to log into the Arena Application after being created to update their password.

* Reset your expired password in Arena.

* Check with the Arena Admin on the resetting of the passwords

