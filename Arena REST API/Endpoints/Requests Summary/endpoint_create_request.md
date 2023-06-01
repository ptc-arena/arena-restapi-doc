# POST Request Create
/requests

In all cases, numberSequencePrefix is required. If a default numberSequencePrefix is associated with the specified request category, not specifying a  numberSequencePrefix will result in automatically selecting the default.  

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Requests and Responses
Create Request.

POST /requests

**Request** 

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
**Response** 

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
