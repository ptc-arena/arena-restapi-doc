# POST Log In


/login

This logs a valid user into the Arena System and once the authentication is successful, a JSON response with an access token is returned. The token needs to be set in the headers of all subsequent requests for them to be processed successfully. The API client should add an HTTP header with name "arena_session_id", the same cookie name as in the Arena Web Application. Note that if you do not specify a workspace_id value in the call, the API user will log in to its current workspace, or whichever it was last logged into.

The response to each Log In request includes the value "workspaceRequestLimit" which is the maximum number of API requests allowed for your workspace during a 24\-hour period. For all responses in the session, the remaining number of API requests for the current period and the scheduled time for resetting of the count are included in the http headers.

* The access token has the same expiration behavior for the cookie token in the Arena web application. 

* If your company uses Single Sign\-On \(SSO\) to access Arena, you should use a dedicated Integration or Partner user to access the Arena REST API.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| content\-type | application/json |   |

## Sample Request Body
```
{  
   "email":"user@customer.com",
   "password":"xxxx",
   "workspaceId":123456789
}
```
## Optional Field
| workspaceId | If a valid workspace ID is provided and the user has access to this workspace, the active workspace after successful login will be the one identified by this ID. Arena recommends using the workspace ID to ensure connection to the expected workspace. |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body


/login

```
{  
   "arena_session_id":"LABS-MXQKenjxWmyUIlJTKwQDfimkZksjpkO0|",
   "workspaceId":123456789,
   "workspaceName":"EveryRoad GPS",
   "workspaceRequestLimit":1000
}
```
Request with bad username, password, or workspace ID

```

{  
   "status":400,
   "errors":[  
      {  
         "code":4001,
         "message":"The username, password or workspace ID is not valid or you are not allowed to log in due to IP restriction."
      }
   ]
}
```
