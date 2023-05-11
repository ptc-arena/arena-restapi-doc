# GET Outbound-Events Integration Events


/outboundevents/&lt;GUID&gt;/events

Returns all the events for a specific outbound event integration.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all items where results should begin. All items before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up to 400 objects.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| resourcesReconciled<br> | Boolean<br> | Indicates if an event is reconciled. If set equal to true it returns only events that are reconciled.<br> |

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

## Sample Response Body
Get all  events associated with a specific outbound event integration.



GET /outboundevents/&lt;GUID&gt;/events

```
{
    "count": 6,
    "results": [
        {
            "creationDateTime": "2021-08-28T05:36:50Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "R9TCV8TK7ALL4N6P8NY5",
            "resourcesReconciled": false,
            "status": "NEEDS_UPDATE",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Queues all Changes with a category of Manufacturing Change Order that move from lifecycle status of Submitted or Approved to Effective.",
                    "guid": "M4O7Q3OF25GDWFYH0JPT",
                    "name": "Manufacturing Change Order Release",
                    "resource": "CHANGE"
                }
            ]
        },
        {
            "creationDateTime": "2021-08-26T22:42:43Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "ASCVERC3QT44N6P8R6HC",
            "resourcesReconciled": false,
            "status": "NEEDS_UPDATE",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Intended to queue up instances of Corrective Action Reports transitioning from the Corrective Action Plan Approved? step to the Corrective Action step.",
                    "guid": "L3N6P2NE14FCVEXGZIIQ",
                    "name": "Corrective Action Report: Plan Step Approval",
                    "resource": "QUALITY"
                }
            ]
        },
        {
            "creationDateTime": "2021-08-26T22:28:58Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "2K4N6J4VILWWFYH0JYA9",
            "resourcesReconciled": false,
            "status": "NEEDS_UPDATE",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Intended to queue up instances of Corrective Action Reports transitioning from the Corrective Action Plan Approved? step to the Corrective Action step.",
                    "guid": "L3N6P2NE14FCVEXGZIIQ",
                    "name": "Corrective Action Report: Plan Step Approval",
                    "resource": "QUALITY"
                }
            ]
        },
       ...
    ]
}
```
Get all reconciled vents associated with a specific outbound event integration.

GET /outboundevents/&lt;GUID&gt;/events?resourcesReconciled=true

```
{
    "count": 3,
    "results": [
        {
            "creationDateTime": "2021-08-06T21:49:40Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "4M6P8L6XKNYYH0J2L10Y",
            "resourcesReconciled": true,
            "status": "RECONCILED",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Queues all Changes with a category of Manufacturing Change Order that move from lifecycle status of Submitted or Approved to Effective.",
                    "guid": "M4O7Q3OF25GDWFYH0JPT",
                    "name": "Manufacturing Change Order Release",
                    "resource": "CHANGE"
                }
            ]
        },
        {
            "creationDateTime": "2021-08-18T18:22:56Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "0I2L4H2TGJUUDWFYHXJX",
            "resourcesReconciled": true,
            "status": "RECONCILED",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Queues up all Items that move into the Design Verification Lifeycle phase.",
                    "guid": "R9TCV8TK7ALI1K3M5OQM",
                    "name": "Design Verification",
                    "resource": "ITEM"
                }
            ]
        },
        {
            "creationDateTime": "2021-08-09T05:27:28Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "eventType": "OUTBOUND_EVENT",
            "guid": "2K4N6J4VILWWFYH0JZWU",
            "resourcesReconciled": true,
            "status": "RECONCILED",
            "triggers": [
                {
                    "action": "WORKFLOW",
                    "description": "Queues all Changes with a category of Manufacturing Change Order that move from lifecycle status of Submitted or Approved to Effective.",
                    "guid": "M4O7Q3OF25GDWFYH0JPT",
                    "name": "Manufacturing Change Order Release",
                    "resource": "CHANGE"
                }
            ]
        }
    ]
}
```
