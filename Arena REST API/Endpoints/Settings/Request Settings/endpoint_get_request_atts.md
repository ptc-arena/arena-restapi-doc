# GET Request Attributes


/settings/requests/attributes

Returns   available for Requests. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of a request. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of a request. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting requests. |

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
Get all request attributes with possible values included



GET /settings/requests/attributes?includePossibleValues=true

```
 

{
    "count": 22,
    "results": [
        {
            "allowsExplicitNullValue": false,
            "apiName": "category",
            "creatable": true,
            "custom": false,
            "description": "Engineering Change Requests should have this assigned category.",
            "developerNotes": "Defaults to -uncategorized- if no default is set",
            "editable": true,
            "example": "E.g., Engineering Change Requests",
            "fieldType": "OBJECT",
            "global": true,
            "guid": "XFZI1I1HDQ8VEXGZI1EQ",
            "inViews": [
                "REQUEST_SUMMARY"
            ],
            "name": "Category",
            "required": true,
            "searchable": true
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "creationDateTime",
            "creatable": false,
            "custom": false,
            "editable": false,
            "fieldType": "DATETIME",
            "global": true,
            "inViews": [
                "REQUEST_SUMMARY"
            ],
            "name": "Creation Date",
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "creator",
            "creatable": false,
            "custom": false,
            "editable": false,
            "fieldType": "OBJECT",
            "global": true,
            "inViews": [
                "REQUEST_SUMMARY"
            ],
            "name": "Creator",
            "searchable": true
        },
        ...
    ]
}
```
