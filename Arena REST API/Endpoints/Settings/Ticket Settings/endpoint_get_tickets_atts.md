# GET Tickets Attributes


/settings/tickets/attributes

Returns   available for Tickets. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a ticket.<br>If this is set to false, it returns only non\-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a ticket. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting tickets.<br> |

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
Get all tickets attributes with possible values included



GET /settings/tickets/attributes

```
{
    "count": 19,
    "results": [
        {
            "active": true,
            "allowsExplicitNullValue": true,
            "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
            "creatable": true,
            "custom": true,
            "deleted": false,
            "description": "Components",
            "editable": true,
            "example": "1",
            "fieldType": "SINGLE_LINE_TEXT",
            "global": true,
            "guid": "6O8RAN8ZMP6O7Q9SBUGT",
            "maxLength": 1000,
            "name": "Components",
            "required": false,
            "revisionControlled": true,
            "searchable": true,
            "visibleWhenBlank": true
        },
        {
            "active": true,
            "allowsExplicitNullValue": true,
            "apiName": "5N7Q9M7YLO5N6P8RATF6",
            "creatable": true,
            "custom": true,
            "deleted": false,
            "description": "Labels",
            "editable": true,
            "example": "1",
            "fieldType": "SINGLE_LINE_TEXT",
            "global": true,
            "guid": "5N7Q9M7YLO5N6P8RATF6",
            "maxLength": 1000,
            "name": "Labels",
            "required": false,
            "revisionControlled": true,
            "searchable": true,
            "visibleWhenBlank": true
        },
        {
            "active": true,
            "allowsExplicitNullValue": true,
            "apiName": "ASCVERC3QTASBUDWFYJ0",
            "creatable": true,
            "custom": true,
            "deleted": false,
            "description": "Reason",
            "editable": true,
            "example": "1",
            "fieldType": "MULTI_LINE_TEXT",
            "global": true,
            "guid": "ASCVERC3QTASBUDWFYJ0",
            "maxLength": 4000,
            "name": "Reason",
            "required": false,
            "revisionControlled": true,
            "searchable": true,
            "visibleWhenBlank": true
        },
        ...
}
```
