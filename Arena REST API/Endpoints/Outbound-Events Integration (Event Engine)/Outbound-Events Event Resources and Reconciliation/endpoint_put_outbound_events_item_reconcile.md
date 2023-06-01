# PUT Outbound-Event Event Item Reconcile
/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

Marks an item in an event as reconciled if reconciled is set to true within the request body.

The user must be an integration administrator for the integration in order to perform this activity.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
Request body with reonciled set to true marks an item in a specific event as reconciled.

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
