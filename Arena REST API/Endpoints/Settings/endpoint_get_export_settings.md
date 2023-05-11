# GET Export Setting Attributes


/settings/export/attributes

Returns  attributes available for an Item export definition. By adding a parameter of includePossibleValues set to true and , the endpoint returns a single unique Item attribute.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which can be set during creation of an item. The default value is false. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which can be set during update of an item. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting items. |
| world | items | If set to items, returns the options and criteria attributes.  |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all export attributes with possible values included for the items world.



GET /settings/export/attributes?includePossibleValues=true&world=items

```
{
    "count": 9,
    "results": [
        {
            "allowsExplicitNullValue": false,
            "apiName": "creationDateTime",
            "creatable": false,
            "editable": false,
            "fieldType": "DATETIME",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "creator",
            "creatable": false,
            "editable": false,
            "fieldType": "OBJECT",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "criteria",
            "creatable": true,
            "editable": false,
            "fieldType": "OBJECT",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "required": false,
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "description",
            "creatable": true,
            "editable": false,
            "fieldType": "SINGLE_LINE_TEXT",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "maxLength": 4000,
            "required": false,
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "guid",
            "creatable": false,
            "editable": false,
            "fieldType": "GUID",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "name",
            "creatable": true,
            "editable": false,
            "fieldType": "SINGLE_LINE_TEXT",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "maxLength": 100,
            "required": true,
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "number",
            "creatable": false,
            "editable": false,
            "fieldType": "NUMBER",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "options",
            "creatable": true,
            "editable": false,
            "fieldType": "OBJECT",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "required": false,
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "world",
            "creatable": true,
            "editable": false,
            "fieldType": "FIXED_DROP_DOWN",
            "inViews": [
                "EXPORT_SUMMARY"
            ],
            "possibleValues": [
                "ITEMS"
            ],
            "required": true,
            "searchable": false
        }
    ]
}
```
