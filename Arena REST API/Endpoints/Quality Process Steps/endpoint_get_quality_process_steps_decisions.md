# GET Quality Process Step Decisions
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/decisions

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/decisions/&lt;GUID&gt;

Returns the decisions of users in a Quality Process sign-off step when given the GUID of the Quality Process and the GUID of the Quality sign-off step.

If appended with a valid decision GUID from the above, the endpoint returns a specific decision from a specific user of a specific step within a specific Quality Process.

The new property decision only appears in Quality sign-off steps.

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get decisions for a given quality process sign-off step where all users are required to sign off.

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/decisions

```
{
    "count": 4,
    "results": [
        {
            "comments": "Thanks for spearheading this case Heidi.",
            "decision": "APPROVED",
            "decisionDateTime": "2021-11-28T10:09:57Z",
            "decisionType": "ALL_REQUIRED",
            "group": {
                "guid": "DVFYHUF6TW2P8RATCFGK",
                "name": "Quality Process Approval Group"
            },
            "guid": "VDXGZCXOBEK5O7Q9AQQ2",
            "user": {
                "email": "rhatcher@everyroadgps.com",
                "fullName": "Richard Hatcher",
                "guid": "M4O7Q3OF25M5O7Q9AQQR"
            }
        },
        {
            "comments": null,
            "decision": "APPROVED",
            "decisionDateTime": "2021-11-28T10:11:32Z",
            "decisionType": "ALL_REQUIRED",
            "group": {
                "guid": "DVFYHUF6TW2P8RATCFGK",
                "name": "Quality Process Approval Group"
            },
            "guid": "4M6P8L6XKNTEXGZIRHOU",
            "user": {
                "email": "rborger@everyroadgps.com",
                "fullName": "Rachael Borger",
                "guid": "VDXGZCXOBEVEXGZIRHOJ"
            }
        },
        {
            "comments": "Please submit an ECR to ensure all preventative measures have been taken. Thanks.",
            "decision": "APPROVED",
            "decisionDateTime": "2021-11-28T10:08:04Z",
            "decisionType": "ALL_REQUIRED",
            "group": {
                "guid": "DVFYHUF6TW2P8RATCFGK",
                "name": "Quality Process Approval Group"
            },
            "guid": "ASCVERC3QTZK3M5OXNUW",
            "user": {
                "email": "ecanard@everyroadgps.com",
                "fullName": "Eleanor Canard",
                "guid": "1J3M5I3UHK1K3M5OXNUV"
            }
        },
        {
            "comments": null,
            "decision": "APPROVED",
            "decisionDateTime": "2021-11-28T10:07:13Z",
            "decisionType": "ALL_REQUIRED",
            "group": {
                "guid": "DVFYHUF6TW2P8RATCFGK",
                "name": "Quality Process Approval Group"
            },
            "guid": "5N7Q9M7YLOUFYH0JSIP0",
            "user": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            }
        }
    ]
}
```
Get decisions  for a given quality process sign-off step where only one user is required to sign off.

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/decisions

```
{
    "count": 2,
    "results": [
        {
            "comments": null,
            "decision": null,
            "decisionDateTime": null,
            "decisionType": "ONE_REQUIRED",
            "guid": "ASCVERC3QTZK3M5OXNUW",
            "user": {
                "email": "ecanard@everyroadgps.com",
                "fullName": "Eleanor Canard",
                "guid": "1J3M5I3UHK1K3M5OXNUV"
            }
        },
        {
            "comments": null,
            "decision": "APPROVED",
            "decisionDateTime": "2021-11-28T09:49:01Z",
            "decisionType": "ONE_REQUIRED",
            "guid": "5N7Q9M7YLOUFYH0JSIP0",
            "user": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            }
        }
    ]
}
```
Get a specific decision from the existing decisions of a sign-off step.

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;/decisions/&lt;GUID&gt;

```
{
    "comments": "While I understand the issue is a high priority for our Canada team, I am not willing to budge on this issue until the core issue is resolved. Otherwise this issue will come up again.",
    "decision": "REJECTED",
    "decisionDateTime": "2021-11-28T10:14:20Z",
    "decisionType": "ALL_REQUIRED",
    "guid": "5N7Q9M7YLOUFYH0JSIP0",
    "user": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
Returns an error if any GUID is not valid

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
