# GET Export Run File Content (Download)
/exports/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;/content

Streams the content of an export file generated from an export run with a given GUID. 

* Export results are saved in Arena and expire after 60 days. Once expired, the results files are deleted in Arena and are no longer available.

* Export Limits: If the criteria return more than 20,000 items, then an error shall be returned. If the criteria return more than 5,000 item, and BOM and FILES view are included as exportViews, then an error shall be returned

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Downloads the export file.

GET /exports/&lt;export definition GUID&gt;/runs/&lt;export run GUID&gt;/files/&lt;export file GUID&gt;/content

```
Streams a zip file containing the CSV or JSON export files.
```
request made by a user who did not initiate the export run

```
{  
   "status":403,
   "errors":[  
      {  
         "code":3024,
         "message":"Either you do not have privileges to access the requested data or it does not exist."
      }
   ]
}
```
request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"L3N6PX663K3K3HOBOOT0 \" is not valid."
      }
   ]
}
```
