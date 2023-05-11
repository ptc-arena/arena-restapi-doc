# PUT Outbound-Event Event Quality Reconcile


/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/qualityprocesses/&lt;GUID&gt;

Marks a change in an event as reconciled if reconciled is set to true within the request body.

The user must be an integration administrator for the integration in order to perform this activity.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
Request body with reonciled set to true marks a quality process in a specific event as reconciled.

```
{
    "reconciled": true
}
```
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

## Sample Responses
Marks as reconciled the specific quality process within an a specific event of a specific outbound\-event integration.



/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/qualityprocesses/&lt;GUID&gt;

```
{
    "guid": "UCWFYBWNADWSBUDWPF1I",
    "postEvent": {
        "currentStep": {
            "guid": "ZH1K3G1SFI1XGZI1UK6H",
            "name": "Corrective Action"
        }
    },
    "preEvent": {
        "currentStep": {
            "guid": "YG0J2F0REH0WFYH0TJ56",
            "name": "Corrective Action Plan Approved?"
        }
    },
    "reconciled": true,
    "reconciledDatetime": "2021-09-11T01:06:50Z",
    "reconciledUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
If the request body has an reconciled value of false, the response would resemble below.

```
{
    "guid": "UCWFYBWNADWSBUDWPF1I",
    "postEvent": {
        "currentStep": {
            "guid": "ZH1K3G1SFI1XGZI1UK6H",
            "name": "Corrective Action"
        }
    },
    "preEvent": {
        "currentStep": {
            "guid": "YG0J2F0REH0WFYH0TJ56",
            "name": "Corrective Action Plan Approved?"
        }
    },
    "reconciled": false
}
```
