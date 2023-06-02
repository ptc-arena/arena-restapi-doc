# GET Request Category Attributes
/settings/requests/categories/&lt;GUID&gt;/attributes

Returns  Attributes available for a Request category with a given GUID. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |
| creatableOnly  | true or false  | If this is set to true, it returns only creatable attributes, which are settable during creation of a request.If this is set to false, it returns only non-creatable attributes.<br>   |
| editableOnly  | true or false  | If this is set to true, it returns only editable attributes, which are settable during update of a request. The default value is false.  |
| searchableOnly  | true or false  | If this is set to true, it returns only searchable attributes, which are searchable when getting requests.  |

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
Get all attributes available for a request category with a given GUID

GET /settings/requests/categories/GUID/attributes

```
 

{
    "count": 19,
    "results": [
        {
            "active": true,
            "allowsExplicitNullValue": false,
            "apiName": "R9TCVCVB7K1J2L4NMPZV",
            "creatable": true,
            "custom": true,
            "deleted": false,
            "editable": true,
            "fieldType": "FIXED_DROP_DOWN",
            "global": false,
            "guid": "R9TCVCVB7K1J2L4NMPZV",
            "multiSelect": false,
            "name": "Urgency",
            "origin": {
                "guid": "UCWFYFYEAN6GZI1JVQS0",
                "name": "Compliance Change Request"
            },
            "possibleValues": [
                "Critical",
                "High",
                "Medium",
                "Low"
            ],
            "required": true,
            "searchable": true
        },
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
            "origin": {
                "guid": "R9TCVCVB7K3DWFYH1HJ5",
                "name": "-uncategorized-"
            },
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
            "origin": {
                "guid": "R9TCVCVB7K3DWFYH1HJ5",
                "name": "-uncategorized-"
            },
            "searchable": false
        },
        ...
    ]
} 
```
