# Connecting and Permissions
Connect to the Arena API service by providing your Arena login credentials \(username and password\) in a Log In request. The API service returns an access token which must be included in the header of all subsequent requests for the session. A session will timeout 90 minutes after the last action and the token will thereafter be invalid.<br>

**The privileges of a user logging into the API service are the same as when logging into Arena.** That is, a read-only user cannot write any information to a PLM workspace, so a read-only user cannot write any information to the workspace via the API service. All requests \(except Healthcheck and Log Out\) are subject to privilege verification.

**Recommended best practices for connecting to the Arena API:** 

* Use a dedicated user to access the Arena API. And more broadly, use a dedicated user for each  integration connected to your Arena workspace.

* Don’t log in twice as the same user at the same time. Logging in a second time will cancel the first session and the first access token will not work.

* Log in to the API, perform whatever actions you desire, then log out of the API when you are done.

* Only Employee and Partner users can access the Arena REST API. Supplier users do not have access privileges.

* If your company uses Single Sign-On (SSO) to access Arena, you should use a dedicated Integration or Partner user to access the Arena REST API.

