# Successes and Errors
As much as possible, Arena attempts to use appropriate HTTP status codes to indicate the general class of problem, and this status code is repeated in the response. The following two tables give supported success status codes and their meanings, and supported error status codes and their meanings.


| Success Code  | Meaning  |
|  --- |  --- | 
| 200 OK  | default success message  |
| 201 Created  | success and new entity created  |
| 204 No content  | Success but no content in response \(e.g. DELETE Item\)  |


| Error Code  | Meaning  |
|  --- |  --- | 
| 400 Bad request  | returned if there is a syntax error in the request  |
| 403 Forbidden  | returned if the user doesn’t have proper privileges to perform them  |
| 401 Unauthorized  | returned if the requests require valid access token, but no valid access token is specified in http headers  |
| 404 Resource not found  | returned if the endpoint of a request is not supported  |
| 409 Item number already exists  | returned if the item number already exists and duplicate item numbers are not allowed in the workspace.  |
| 415 Unsupported media type  | returned if no content-type/wrong content-type is specified in http headers  |
| 429 Too may requests  | returned if the maximum API requests limit has been reached for 24-hour period  |

