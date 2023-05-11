# GET Triggers


/settings/integrations/triggers

Returns allthe triggers of a workspace.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all changes where results should begin. All changes before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up 400 changes.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | The name of the Trigger.<br> |
| resource<br> | string<br> | The resource of the Trigger. Currently supported resources:<br>ITEM<br>REQUEST<br>CHANGE<br>QUALITY<br> |
| action<br> | string<br> | The action of the Trigger. Supported actions:<br>CREATE<br>EDIT<br>WORKFLOW<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi\-colon.

When using a semi\-colon to separate values in a FIXED_DROP_DOWN search, note that the semi\-colon will always act as an OR. This is relevant when performing a Multi\-Select search.

For example with FIXED_DROP_DOWN, multiselect = True: GET /Items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN contains Option 1 OR Option 2 \(or both\). On the other hand FIXED_DROP_DOWN, multiselect=False: GET /items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN equals Option 1 OR Option 2.

Search in Zulu format is supported for custom attribute field type Date.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

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
Get all triggers in a workspace



GET /settings/integrations/triggers

```
{
    "count": 4,
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
        },
        {
            "action": "WORKFLOW",
            "creationDatetime": "2021-08-26T22:50:27Z",
            "creator": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "Queues Temporary Changes once they're effective.",
            "guid": "O6Q9S5QH47IFYH0J2LLA",
            "lastModifiedDateTime": "2021-08-26T22:51:00Z",
            "modifyUser": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Deviations",
            "resource": "CHANGE"
        },
        {
            "action": "WORKFLOW",
            "creationDatetime": "2021-08-06T21:38:31Z",
            "creator": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "Queues all Changes with a category of Manufacturing Change Order that move from lifecycle status of Submitted or Approved to Effective.",
            "guid": "M4O7Q3OF25GDWFYH0JPT",
            "lastModifiedDateTime": "2021-08-26T22:46:54Z",
            "modifyUser": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Manufacturing Change Order Release",
            "resource": "CHANGE"
        },
        {
            "action": "WORKFLOW",
            "creationDatetime": "2021-08-18T18:20:48Z",
            "creator": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "Queues up all Items that move into the Design Verification Lifeycle phase.",
            "guid": "R9TCV8TK7ALI1K3M5OQM",
            "lastModifiedDateTime": "2021-08-26T22:45:35Z",
            "modifyUser": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Design Verification",
            "resource": "ITEM"
        },
        {
            "action": "CREATE",
            "creationDatetime": "2023-01-26T03:43:21Z",
            "creator": {
                "email": null,
                "fullName": "Heidi Walker",
                "guid": "9RBUZOR8OFWFYH0JSIPJ"
            },
            "description": null,
            "guid": "R9TCH69Q6X85O7Q9SBT0",
            "lastModifiedDateTime": null,
            "modifyUser": null,
            "name": "Create Requests",
            "resource": "REQUEST"
        }
    ]
}
```
Get  triggers with a resource of QUALITY and an action of WORKFLOW



GET settings/integrations/triggers?resource=QUALITY&action=WORKFLOW

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
