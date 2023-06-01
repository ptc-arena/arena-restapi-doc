# GET Request Status Change Attributes
settings/requests/statuschangeattributes

This endpoint returns attributes used when modifying the status of a Request. These attributes can be utilized in the POST requests/statuschanges endpoints.

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
Get the Requests Status Change Attributes.

GET settings/requests/statuschangeattributes

```
{
    "count": 7,
    "results": [
        {
            "allowsExplicitNullValue": false,
            "apiName": "resolutionNotes",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "SINGLE_LINE_TEXT",
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "deferralCode",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "FIXED_DROP_DOWN",
            "multiSelect": false,
            "possibleValues": [
                "Next Version",
                "Future Project",
                "Low Priority",
                "Resources Unavailable"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "status",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "FIXED_DROP_DOWN",
            "possibleValues": [
                "UNSUBMITTED",
                "SUBMITTED",
                "PROMOTED",
                "CLOSED",
                "DEFERRED"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "resolutionCode",
            "creatable": true,
            "custom": false,
            "defaultValue": "Approved [Immediate]",
            "editable": false,
            "fieldType": "FIXED_DROP_DOWN",
            "multiSelect": false,
            "possibleValues": [
                "Approved [Immediate]",
                "Approved [Future]",
                "Rejected",
                "As Designed",
                "Duplicate"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "deferDeadlineDateTime",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "DATETIME",
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "request",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "OBJECT",
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "comment",
            "creatable": true,
            "custom": false,
            "editable": false,
            "fieldType": "SINGLE_LINE_TEXT",
            "searchable": false
        }
    ]
}
```
