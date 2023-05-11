# GET Request Status Change Attributes


settings/requests/statuschangeattributes

This endpoint returns attributes used when modifying the status of a Request. These attributes can be utilized in the POST requests/statuschanges endpoints.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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
