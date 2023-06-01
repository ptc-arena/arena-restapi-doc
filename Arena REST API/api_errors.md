# Successes and Errors
As much as possible, Arena attempts to use appropriate HTTP status codes to indicate the general class of problem, and this status code is repeated in the response. The following two tables give supported success status codes and their meanings, and supported error status codes and their meanings.


| Success Code<br> | Meaning<br> |
|  --- |  --- | 
| 200 OK<br> | default success message<br> |
| 201 Created<br> | success and new entity created<br> |
| 204 No content<br> | Success but no content in response \(e.g. DELETE Item\)<br> |


| Error Code<br> | Meaning<br> |
|  --- |  --- | 
| 400 Bad request<br> | returned if there is a syntax error in the request<br> |
| 403 Forbidden<br> | returned if the user doesn’t have proper privileges to perform them<br> |
| 401 Unauthorized<br> | returned if the requests require valid access token, but no valid access token is specified in http headers<br> |
| 404 Resource not found<br> | returned if the endpoint of a request is not supported<br> |
| 409 Item number already exists<br> | returned if the item number already exists and duplicate item numbers are not allowed in the workspace.<br> |
| 415 Unsupported media type<br> | returned if no content-type/wrong content-type is specified in http headers<br> |
| 429 Too may requests<br> | returned if the maximum API requests limit has been reached for 24-hour period<br> |

