# Errors Encountered When Logging Out in the Onshape-Arena Connection
POST /logout

This endpoint is used to authorize the Onshape User with Arena after a session has been established by the POST /login endpoint. If this endpoint cannot establish a session then the Onshape Arena Settings \(Onshape &gt; Settings &gt; Arena\)  will be incomplete and the Mappings will not be able to be refreshed. In addition, the user will not be able to sync Onshape with Arena.


| Status Code<br> | Error Code<br> | Message<br> | Explanation<br> |
|  --- |  --- |  --- |  --- | 
| 401<br> | 401<br> |  ```There is no access token associated with this request or the access token is not valid.```  | The session is no longer valid due to a session being terminated or expired and the integration issues a logout.<br> |

