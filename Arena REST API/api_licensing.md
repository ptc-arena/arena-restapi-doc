# Licensing
To enable the Arena REST API for your account, contact .

Most accounts are allowed a maximum number of requests to the API per 24 hour period, starting at midnight Pacific Time. After the total allowed number of requests is reached, the service will return an error.  All API requests \(except login\), whether successful or not, are counted toward the total. The number of requests allowed varies per workspace. If you feel you need more API requests, contact your Account Executive. 

The http headers of all API responses include the remaining number of API requests for the current period and the scheduled time for resetting of the count are included in the header. For example:




X\-Arena\-Next\-Request\-Limit\-Reset: Fri, 02\-May\-2014 14:22:13 GMT\-0700 \(PDT\) X\-Arena\-Requests\-Remaining: 2

And each response to the Log In request includes the total number of API requests for the period. For example:



"workspaceRequestLimit": 10000

Arena recommends setting up the calling program to read licensing information from response headers, and not make any additional calls when X\-Arena\-Requests\-Remaining gets to 0 until after the Next Request Limit Reset.

