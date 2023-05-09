# GET Change Category Attributes


/settings/changes/categories/&lt;GUID&gt;/attributes

Returns   available for a Change category with a given GUID. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of a change. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of an change. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting changes. |

If this is set to false, it returns only non\-creatable attributes.

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
Get all attributes available for a change category with a given GUID



GET /settings/changes/categories/GUID/attributes

```
{
    "count": 23,
    "results": [
        {
            "allowsExplicitNullValue": true,
            "apiName": "approvalDeadlineDateTime",
            "creatable": true,
            "custom": false,
            "editable": true,
            "fieldType": "DATETIME",
            "global": true,
            "inViews": [
                "CHANGE_SUMMARY"
            ],
            "name": "Approval Deadline",
            "origin": {
                "guid": "CUEXGTE5SVEO7Q5CCD1T",
                "name": "-uncategorized-"
            },
            "required": false,
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "canceledDateTime",
            "creatable": false,
            "custom": false,
            "editable": false,
            "fieldType": "DATETIME",
            "global": true,
            "inViews": [
                "CHANGE_SUMMARY"
            ],
            "name": "Canceled On",
            "origin": {
                "guid": "CUEXGTE5SVEO7Q5CCD1T",
                "name": "-uncategorized-"
            },
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "category",
            "creatable": true,
            "custom": false,
            "developerNotes": "Defaults to -uncategorized- if no default is set",
            "editable": true,
            "fieldType": "OBJECT",
            "global": true,
            "guid": "I0K3MZKBY1J6P8RATCV5",
            "inViews": [
                "CHANGE_SUMMARY"
            ],
            "name": "Category",
            "origin": {
                "guid": "CUEXGTE5SVEO7Q5CCD1T",
                "name": "-uncategorized-"
            },
            "required": false,
            "searchable": true
        },
        ...        
    ]
}
```
