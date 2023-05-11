# PUT Outbound-Event Event Requests Reconcile


/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/requests/&lt;GUID&gt;

Marks a request in an event as reconciled if reconciled is set to true within the request body.

The user must be an integration administrator for the integration in order to perform this activity.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
Request body with reconciled set to true marks a Request in a specific event as reconciled.

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
Marks as reconciled the specific request within an a specific event of a specific outbound\-event integration.



/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;/requests/&lt;GUID&gt;

```
{
    "guid": "N5P8D25M2T43M5OZP7I8",
    "postEvents": [
        {
            "additionalAttributes": [
                {
                    "apiName": "O6Q9E36N3UBTCVCZLWDP",
                    "fieldType": "FIXED_DROP_DOWN",
                    "guid": "O6Q9E36N3UBTCVCZLWDP",
                    "name": "Urgency",
                    "value": "Critical"
                },
                {
                    "apiName": "P7RAF47O4VCUDWD0MXE8",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "P7RAF47O4VCUDWD0MXE8",
                    "name": "Expected Completion Date",
                    "value": "31/10/2024"
                }
            ],
            "category": {
                "guid": "SAUDI7AR7YHRAT5C5MA6"
            },
            "problem": "We need to reproduce the Ferrite Cores used in the Project 9708",
            "requestedAction": "Use The Artemis notes to relayer the fibers based on the 1874 Archives."
        }
    ],
    "preEvents": [
        {
            "additionalAttributes": [
                {
                    "apiName": "O6Q9E36N3UBTCVCZLWDP",
                    "fieldType": "FIXED_DROP_DOWN",
                    "guid": "O6Q9E36N3UBTCVCZLWDP",
                    "name": "Urgency",
                    "value": null
                },
                {
                    "apiName": "P7RAF47O4VCUDWD0MXE8",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "P7RAF47O4VCUDWD0MXE8",
                    "name": "Expected Completion Date",
                    "value": null
                }
            ],
            "category": {
                "guid": "1J3MRGJ0G7Q0J2ELEVIF"
            },
            "problem": "We need to reproduce the Ferrite Cores used in the Apollo Program",
            "requestedAction": "Use The Artemis notes to relayer the fibers"
        }
    ],
    "reconciled": true,
    "reconciledDatetime": "2022-11-24T08:46:45Z",
    "reconciledUser": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "9RBUZOR8OFWFYH0JSIPJ"
    }
}
```
If the request body has a reconciled value of false, the response would resemble below.

```
{
    "guid": "4M6PUJM3JALK3M5G6PVS",
    "postEvents": [
        {
            "lifecycleStatus": {
                "type": "SUBMITTED"
            }
        }
    ],
    "preEvents": [
        {
            "lifecycleStatus": {
                "type": "PROMOTED"
            }
        }
    ],
    "reconciled": false
}
```
