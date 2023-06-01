# PUT Request Edit
/requests/&lt;GUID&gt;

Updates attribute information for a Request with a given GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null

| Name<br> |   | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set problem or requestedAction to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

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

## Sample Requests and Responses
Edit a Request.

/requests/&lt;GUID&gt;

**Request** 

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
**Response** 

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

**Request** 

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
**Response** 

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
