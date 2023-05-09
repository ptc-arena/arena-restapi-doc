# PUT Request Edit


/requests/&lt;GUID&gt;

Updates attribute information for a Request with a given GUID. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name |   | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set problem or requestedAction to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

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

## Sample Requests and Responses
Edit a Request.

/requests/&lt;GUID&gt;



```
{
    "category": {
        "guid": "GYI1KXI9WZISBU9GGH53"
    },
    "title": "Melted Bezels on Model 400",
    "problem": "Unit PCB is overheating",
    "requestCode": "Performance"
}
```


```
{
    "category": {
        "guid": "GYI1KXI9WZISBU9GGH53",
        "name": "Document Change Request"
    },
    "creationDateTime": "2021-09-06T05:36:54Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "deferDeadlineDateTime": null,
    "deferralCode": null,
    "dispositionType": null,
    "evaluatorGroup": {
        "guid": "SAUDW9UL8BS9SBUDUHW0",
        "name": "ECR Review Board"
    },
    "guid": "SAUDW9UL8BUTCVRBA53C",
    "lifecycleDateTime": "2021-09-06T05:36:54Z",
    "lifecycleStatus": {
        "type": "UNSUBMITTED"
    },
    "number": "ECR-000009",
    "problem": "Unit PCB is overheating",
    "requestCode": "Performance",
    "requestedAction": "Add Additional Fans and Heat Sinks",
    "resolutionCode": null,
    "submissionDateTime": null,
    "submitter": null,
    "title": "Melted Bezels on Model 400"
}
```
Sets a Request attribute to null.

PUT /requests/&lt;GUID&gt;?setnull=true



```
{
    "category": {
        "guid": "GYI1KXI9WZISBU9GGH53"
    },
    "title": "Melted Bezels on Model 400",
    "problem": null,
    "requestCode": "Performance"
}
```


```
{
    "category": {
        "guid": "GYI1KXI9WZISBU9GGH53",
        "name": "Document Change Request"
    },
    "creationDateTime": "2021-09-06T05:36:54Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "deferDeadlineDateTime": null,
    "deferralCode": null,
    "dispositionType": null,
    "evaluatorGroup": {
        "guid": "SAUDW9UL8BS9SBUDUHW0",
        "name": "ECR Review Board"
    },
    "guid": "SAUDW9UL8BUTCVRBA53C",
    "lifecycleDateTime": "2021-09-06T05:36:54Z",
    "lifecycleStatus": {
        "type": "UNSUBMITTED"
    },
    "number": "ECR-000009",
    "problem": null,
    "requestCode": "Performance",
    "requestedAction": "Add Additional Fans and Heat Sinks",
    "resolutionCode": null,
    "submissionDateTime": null,
    "submitter": null,
    "title": "Melted Bezels on Model 400"
}
```
Request with invalid GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3011,
            "message":"The guid \"ASCVERC3QTCFYGPWW1WCS\" is not valid"
        }
    ]
}
```
