# GET Request Item Attributes
/settings/requests/items/attributes

Returns  Attributes  available for Requests. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includePossibleValues  | true or false  | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.  |
| creatableOnly  | true or false  | If this is set to true, it returns only creatable attributes, which are settable during the addition of an item to a request.If this is set to false, it returns only non-creatable attributes.<br>   |
| editableOnly  | true or false  | If this is set to true, it returns only editable attributes, which are settable during the update of a request-item relationship. The default value is false.  |
| searchableOnly  | true or false  | If this is set to true, it returns only searchable attributes, which are searchable when getting requests-item associations.  |

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
Get all modified item attributes, showing all possible values

GET /settings/requests/items/attributes?includePossibleValues=true

```
{
    "count": 3,
    "results": [
        {
            "allowsExplicitNullValue": false,
            "apiName": "guid",
            "creatable": false,
            "custom": false,
            "editable": false,
            "fieldType": "GUID",
            "inViews": [
                "REQUEST_ITEMS"
            ],
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "item",
            "creatable": true,
            "custom": false,
            "developerNotes": "Item Revision that is affected",
            "editable": false,
            "fieldType": "OBJECT",
            "inViews": [
                "REQUEST_ITEMS"
            ],
            "required": false,
            "searchable": false
        },
        {
            "allowsExplicitNullValue": false,
            "apiName": "notes",
            "creatable": true,
            "editable": true,
            "fieldType": "MULTI_LINE_TEXT",
            "inViews": [
                "REQUEST_ITEMS"
            ],
            "maxLength": 4000,
            "searchable": false
        }
    ]
}
```
