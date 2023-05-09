# POST Request Create


/requests

In all cases, numberSequencePrefix is required. If a default numberSequencePrefix is associated with the specified request category, not specifying a  numberSequencePrefix will result in automatically selecting the default.  

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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
Create Request.



POST /requests



```
{
    "category": {
        "guid": "HZJ2LYJAX0JTCVAHHI66"
    },
    "creatorParticipation": false,
    "evaluatorGroup": {
        "guid": "SAUDW9UL8BS9SBUDUHW0"
    },
    "numberSequencePrefix": {
        "value": "ECR-"
    },
    "title": "Melted Bezels on Model 360",
    "problem": "Unit is overheating",
    "requestCode": "Cost",
    "requestedAction": "Add Additional Fans and Heat Sinks"
}
```


```
{
    "category": {
        "guid": "HZJ2LYJAX0JTCVAHHI66",
        "name": "Engineering Change Request"
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
    "problem": "Unit is overheating",
    "requestCode": "Cost",
    "requestedAction": "Add Additional Fans and Heat Sinks",
    "resolutionCode": null,
    "submissionDateTime": null,
    "submitter": null,
    "title": "Melted Bezels on Model 360"
}
```
