# GET Tickets Templates Attributes


/settings/tickets/templates/&lt;GUID&gt;/attributes

Returns   available for a Tickets template with a given GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop\-DOwn List attributes. The default value is false.<br> |

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
Get all attributes available for a tickets template with a given GUID including all possible values for drop\-down list attributes.



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
