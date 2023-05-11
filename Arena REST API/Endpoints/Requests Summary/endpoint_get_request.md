# GET Request


/requests/&lt;GUID&gt;

Returns a Request object with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
