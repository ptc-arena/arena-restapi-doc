# GET Tickets Templates Attributes
/settings/tickets/templates/&lt;GUID&gt;/attributes

Returns  Attributes available for a Tickets template with a given GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop-DOwn List attributes. The default value is false.  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all attributes available for a tickets template with a given GUID including all possible values for drop-down list attributes.

GET /settings/tickets/templates/GUID/attributes?includePossibleValues=true

```
{
    "count": 13,
    "results": [
        {
            "allowsExplicitNullValue": false,
            "apiName": "guid",
            "creatable": false,
            "custom": false,
            "editable": false,
            "fieldType": "GUID",
            "inViews": [
                "VERIFY_SUMMARY"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "title",
            "creatable": true,
            "custom": false,
            "editable": true,
            "fieldType": "SINGLE_LINE_TEXT",
            "inViews": [
                "VERIFY_SUMMARY"
            ],
            "required": true,
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "description",
            "creatable": true,
            "custom": false,
            "editable": true,
            "fieldType": "RICH_TEXT",
            "inViews": [
                "VERIFY_SUMMARY"
            ],
            "searchable": false
        },
        ...
    ]
}
```
