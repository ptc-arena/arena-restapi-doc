# PUT Outbound-Event Event Change Reconcile


/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/changes/&lt;GUID&gt;

Marks a change in an event as reconciled if reconciled is set to true within the request body.

The user must be an integration administrator for the integration in order to perform this activity.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
Request body with reonciled set to true marks a change in a specific event as reconciled.

```
{
    "reconciled": true
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Responses
Marks as reconciled the specific change within an a specific event of a specific outbound\-event integration.



/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/changes/&lt;GUID&gt;

```
{
    "guid": "SAUDW9UL8BUXGYEEGQCB",
    "postEvent": {
        "lifecycleStatus": {
            "type": "APPROVED"
        }
    },
    "preEvent": {
        "lifecycleStatus": {
            "type": "SUBMITTED_FOR_APPROVAL"
        }
    },
    "reconciled": true,
    "reconciledDatetime": "2021-09-11T01:02:18Z",
    "reconciledUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
If the request body has a reconciled value of false, the response would resemble below.

```
{
    "guid": "SAUDW9UL8BUXGYEEGQCB",
    "postEvent": {
        "lifecycleStatus": {
            "type": "APPROVED"
        }
    },
    "preEvent": {
        "lifecycleStatus": {
            "type": "SUBMITTED_FOR_APPROVAL"
        }
    },
    "reconciled": false
}
```
