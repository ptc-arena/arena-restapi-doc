# PUT Outbound-Event Event Item Reconcile
/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

Marks an item in an event as reconciled if reconciled is set to true within the request body.

The user must be an integration administrator for the integration in order to perform this activity.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Sample Request Body
Request body with reonciled set to true marks an item in a specific event as reconciled.

```
{
    "reconciled": true
}
```
## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Responses
Marks as reconciled the specific item within an a specific event of a specific outbound-event integration.

/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "I0K3MZKBY1KSBP7DYNR7",
    "postEvent": {
        "guid": "I0K3MZKBY1KSBP7DYNR7"
    },
    "preEvent": null,
    "reconciled": true,
    "reconciledDatetime": "2021-09-10T23:58:21Z",
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
    "guid": "I0K3MZKBY1KSBP7DYNR7",
    "postEvent": {
        "guid": "I0K3MZKBY1KSBP7DYNR7"
    },
    "preEvent": null,
    "reconciled": false
}
```
