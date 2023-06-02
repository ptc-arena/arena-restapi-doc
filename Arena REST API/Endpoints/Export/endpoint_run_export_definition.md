# POST Export Run
/exports/&lt;GUID&gt;/runs

Initiates an Export run based on an existing Export Definition.  Each case is shown below.

NOTES:

* The export run endpoint executes an export definition.

* If the criteria was specified in the export definition, that criteria will be used in the run and cannot be specified in the export run. 

* If the criteria was not specified in the export definition, a criteria must be specified in the export run.

* Export results are saved in Arena and expire after 60 days. Once expired, the results files are deleted in Arena and are no longer available.

* Export Limits: If the criteria return more than 20,000 items, then an error shall be returned. If the criteria return more than 5,000 item, and BOM and FILES view are included as exportViews, then an error shall be returned.

Exports runs can have the following six statuses.


| Export Status  | Description  |
|  --- |  --- | 
| CREATED  | The export run has been created and is queued for processing.  |
| RUNNING  | The export run is processing.  |
| COMPLETE  | The export file is completed and is ready to be downloaded.  |
| DOWNLOADED  | The export file has been downloaded by a user.  |
| FAILED  | The export failed at runtime and there are no results.  |
| ABORTED  | The export run was manually aborted by Arena Technical Support.  |

* If an export has a JSON format and certain Export Options selected it can result in a JSON export file without any content. See About Export Results and the JSON Format.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
* Run Export Definition (Criteria not specified in the export definition so it must be specified in the run)

```
   "criteria":[
      {
         "attribute":"number",
         "operator":"IS_EQUAL_TO",
         "value":"20-0001"
      }
   ]
```
* Run Export Definition (Criterion specified in the export definition so it is not necessary to specify it in the run)

```
{}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Export Run is processing

```
{  
   "completionDateTime":null,  
   "creationDateTime":"2020-03-07T09:32:25Z",
   "creator": {
       "guid":"ASCV96ACN4L4N6P6BG6H"
   },
   "criteria":[
      {
         "attribute":"number",
         "operator":"IS_EQUAL_TO",
         "value":"20-0001"
      }
   ]
   "criteriaResultsCount": 1,
   "guid":"Q8SBPMQS3K0IKBD56MW",
   "number":12,
   "status":"RUNNING"
}
```
Export Run completed

```
{  
   "completionDateTime":"2020-03-07T09:32:30Z",  
   "creationDateTime":"2020-03-07T09:32:25Z",
   "creator": {
       "guid":"ASCV96ACN4L4N6P6BG6H"
   },
   "criteria":[
      {
         "attribute":"number",
         "operator":"IS_EQUAL_TO",
         "value":"20-0001"
      }
   ]
   "criteriaResultsCount": 1,
   "files": [
       {
           "guid": "1J3M0X13EVEUDWMBT049",
           "title": null 
       }
   ],
   "guid":"Q8SBPMQS3K0IKBD56MW",
   "number":12,
   "status":"COMPLETE"
}
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

* A field is not creatable. 

```

{  
   "status":400,
   "errors":[  
      {  
         "code":4004,
         "message":"The attribute \"name1\" is not creatable."
      }
   ]
}
```
* A value in the export definition is invalid.

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
* A required field is missing.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3006,
         "message":"The attribute \"Description\" is required."
      }
   ]
}
```
