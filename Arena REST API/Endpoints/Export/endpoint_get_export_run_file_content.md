# GET Export Run File Content (Download)


/exports/&lt;GUID&gt;/runs/&lt;GUID&gt;/files/&lt;GUID&gt;/content

Streams the content of an export file generated from an export run with a given GUID. 

* Export results are saved in Arena and expire after 60 days. Once expired, the results files are deleted in Arena and are no longer available.

* Export Limits: If the criteria return more than 20,000 items, then an error shall be returned. If the criteria return more than 5,000 item, and BOM and FILES view are included as exportViews, then an error shall be returned

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

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
