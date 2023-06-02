# GET Trigger
/settings/integrations/triggers/&lt;GUID&gt;

Returns a Trigger  with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
