# GET Request Item Attributes
/settings/requests/items/attributes

Returns  Attributes  available for Requests. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during the addition of an item to a request.<br>If this is set to false, it returns only non-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during the update of a request-item relationship. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting requests-item associations.<br> |

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
