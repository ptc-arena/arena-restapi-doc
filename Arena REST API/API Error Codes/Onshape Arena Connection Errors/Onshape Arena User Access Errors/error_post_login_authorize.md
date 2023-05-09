# Errors Encountered When Authorizing an Onshape User
POST /login/authorizeuser

This endpoint is used to authorize the Onshape User with Arena after a session has been established by the POST /login endpoint. If this endpoint cannot establish a session then the Onshape Arena Settings \(Onshape &gt; Settings &gt; Arena\)  will be incomplete and the Mappings will not be able to be refreshed. In addition, the user will not be able to sync Onshape with Arena.


| Status Code | Error Code | Message | Explanation |
|  --- |  --- |  --- |  --- | 
| 400 | 4081 |   | Error occurs when Onshape\-Arena Employee User encounters the following scenarios:    |
| 400 | 4083 |   | The Onshape Arena Employee User has failed to login successfully and the account has been locked for 5 minutes.  |
| 400 | 20001 |   | Onshape Arena Employee User that is being authorized has been disabled. Arena Administrator can enable user under the Arena &gt; Workspace &gt; Settings &gt; Employees &gt; Employee.  |
| 500 | 20000 |   | A login session could not be established through the POST /login endpoint. Arena Administrator can check both the Arena Employee User assigned the WebToken and the Authorize User to make they are configured correctly.  |
| 400 | 20016 |   | Onshape Arena Employee User that is being authorized does not have access to the target workspace. Arena Administrator can grant the user access to the workspace with a Full License and the required access policies.  |
| 400 | 20015 |   | The Onshape Arena User Email does not exist in Arena. Arena Administrator can add the Onshape User as an Arena Full Licensed Employee with the required Access Policies  |

```
Your password has either been reset by an Account Administrator or has expired. Please proceed to the browser-based Arena user interface and configure a new password.
```
* Not performed an initial Arena Login.

* Password has Expired

* Password Reset by Arena Administrator

The solutions for each issue are listed below:

* All Onshape Arena Employee Users are required to log into the Arena Application after being created to update their password.

* Reset your expired password in Arena.

* Check with the Arena Admin on the resetting of the passwords

```
Too many invalid password attempts, account disabled for five minutes.
```
Wait for the lockout time to elapse and try process again.

Note: Don’t share accounts & Reset your password periodically.

```
Insufficient privileges for this user.
```
Onshape Arena Employee User that is being authorized has not logged into Arena for the first time to set their Arena password: All Standard Users created are required to log  into the Arena Application after being created and update their password. The Arena Administrator can assist with this action item.

```
User not authenticated.
```
```
User not authorized for workspace.
```
The login session established through the POST /login endpoint has expired. Restart the process because the POST /login must be re\-executed to establish a new session.

Note: Onshape users that are created as new Full Licensed Employees in Arena are assigned to the Arena Workspace that is being referenced by Onshape. As well as assigned the required access polices.

```
User email address not found.
```
Note: Each Onshape User that is synchronizing to Arena should be created in Arena as a Full License Standard Employee with at least Item & File Read & Edit Policies. 

