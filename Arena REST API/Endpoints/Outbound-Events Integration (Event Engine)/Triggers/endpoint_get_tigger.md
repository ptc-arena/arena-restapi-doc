# GET Trigger
/settings/integrations/triggers/&lt;GUID&gt;

Returns a Trigger  with a given GUID.

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
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get a trigger with a unique GUID

GET /settings/integrations/triggers/&lt;GUID&gt;

```
{
    "count": 1,
    "results": [
        {
            "action": "WORKFLOW",
            "creationDatetime": "2021-08-26T21:51:34Z",
            "creator": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "Intended to queue up instances of Corrective Action Reports transitioning from the Corrective Action Plan Approved? step to the Corrective Action step.",
            "guid": "L3N6P2NE14FCVEXGZIIQ",
            "lastModifiedDateTime": null,
            "modifyUser": null,
            "name": "Corrective Action Report: Plan Step Approval",
            "resource": "QUALITY"
        }
    ]
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
