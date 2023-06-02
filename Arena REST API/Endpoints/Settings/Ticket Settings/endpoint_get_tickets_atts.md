# GET Tickets Attributes
/settings/tickets/attributes

Returns  Attributes available for Tickets. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |
| creatableOnly  | true or false  | If this is set to true, it returns only creatable attributes, which are settable during creation of a ticket.If this is set to false, it returns only non-creatable attributes.<br>   |
| editableOnly  | true or false  | If this is set to true, it returns only editable attributes, which are settable during update of a ticket. The default value is false.  |
| searchableOnly  | true or false  | If this is set to true, it returns only searchable attributes, which are searchable when getting tickets.  |

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
