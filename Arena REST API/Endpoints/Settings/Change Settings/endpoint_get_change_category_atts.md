# GET Change Category Attributes
/settings/changes/categories/&lt;GUID&gt;/attributes

Returns  Attributes available for a Change category with a given GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a change.<br>If this is set to false, it returns only non-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of an change. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting changes.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
