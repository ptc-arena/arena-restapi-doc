# GET Request


/requests/&lt;GUID&gt;

Returns a Request object with a given GUID.

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get a request with a unique GUID

 

GET /requests/&lt;GUID&gt;

```
{
    "category": {
        "guid": "HZJ2LYJAX0JTCVAHHI66",
        "name": "Engineering Change Request"
    },
    "creationDateTime": "2011-07-11T22:55:16Z",
    "creator": {
        "email": "ykeller@arenasolutions.com",
        "fullName": "Yvette Keller",
        "guid": "VDXGZCXOBEVEXGZIWZJK"
    },
    "deferDeadlineDateTime": null,
    "deferralCode": null,
    "dispositionType": null,
    "evaluatorGroup": {
        "guid": "3L5O7K5WJM3K3M5O5JDC",
        "name": "Product Enhancement"
    },
    "guid": "Q8SBU7SJ69SRAT0L94BE",
    "lifecycleDateTime": "2014-10-28T21:20:07Z",
    "lifecycleStatus": {
        "type": "PROMOTED"
    },
    "number": "ECR-000001",
    "problem": "EveryRoad Model 300 is currently mounted directly to a car dashboard through a loop and hook (Velcro) system. Product management has received significant complaints that this mounting system does not work well on certain cars or the owners do not want to have adhesive on their dashboard.",
    "requestCode": "Performance",
    "requestedAction": "Find a method of mounting the EveryRoad GPS Model 300 which:\n1) Is flexible to fit on many different cars\n2) Does not require adhesive to be in direct contact with a car",
    "resolutionCode": "Approved [Immediate]",
    "submissionDateTime": "2011-07-20T22:16:33Z",
    "submitter": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "title": "Alternate Mounting Solution for EveryRoad GPS"
}
      
```
Request with bad GUID

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
