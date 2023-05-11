# POST Import Run


/imports/&lt;GUID&gt;/runs

Initiates an Import run based using an import source file in conjunection with an existing Import Definition.  Each case is shown below.

NOTES:

* The import run endpoint executes an import definition.

* Import results are saved in Arena and expire after 60 days. Once expired, the results files are deleted in Arena and are no longer available.

* Import Limits: COMING SOON.

Import runs can have the following six statuses.


| Import Status<br> | Description<br> |
|  --- |  --- | 
| CREATED<br> | The import run has been created and is queued for processing.<br> |
| RUNNING<br> | The import run is processing.<br> |
| COMPLETE<br> | The import file is completed and is ready to be downloaded.<br> |
| ERROR<br> | The import file has errors.<br> |

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | multipart/form\-data<br> |   |

## Sample Request Body
* Run Import Definition with an Excel worksheet.  Do not commit data to workspace.

```
submitContent:everyscan_spring2023_project_revA.xlsx
submitFileType: EXCEL_WORKSHEET
submitWorsheetName:everyscanBOM
commit: false
```
* Run Import Definition with a CSV file. Commit data to workspace \(assuming there are no errors\).

```
submitContent:updated_parts_for_winter_23_fan.csv
submitFileType: CSV
commit: true
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Run Import Definition with an Excel worksheet.  Do not commit data to workspace.

```
{
    "number": 2,
    "creator": {
        "fullName": "Heidi Walker",
        "email": "hwalker@everyroadgps.com",
        "guid": "9RBUZOR8OFWFYH0JSIPJ"
    },
    "submitFileType": "EXCEL_WORKSHEET",
    "submitWorksheetName": everyscanBOM,
    "status": "CREATED",
    "commit": false,
    "totalCount": 3,
    "successCount": 3,
    "errorCount": 0,
    "guid": "GYI16VYFVMMO7Q9SBN3Q"
}
```
Run Import Definition with a CSV file. Commit data to workspace \(assuming there are no errors\).

```
{
    "number": 2,
    "creator": {
        "fullName": "Heidi Walker",
        "email": "hwalker@everyroadgps.com",
        "guid": "9RBUZOR8OFWFYH0JSIPJ"
    },
    "submitFileType": "CSV",
    "status": "CREATED",
    "commit": true,
    "totalCount": 3,
    "successCount": 3,
    "errorCount": 0,
    "guid": "FE67A3D57DAF4293A1FF"
}
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

* A value in the import definition is invalid.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The specified value \"Changes\" is not a valid option for the attribute \"world\"."
      }
   ]
}
```
