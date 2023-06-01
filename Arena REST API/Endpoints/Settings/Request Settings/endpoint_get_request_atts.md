# GET Request Attributes
/settings/requests/attributes

Returns  Attributes available for Requests. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a request.<br>If this is set to false, it returns only non-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a request. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting requests.<br> |

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
