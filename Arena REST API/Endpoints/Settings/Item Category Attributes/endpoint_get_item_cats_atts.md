# GET Item Category Attributes


/settings/items/categories/&lt;GUID&gt;/attributes

This returns   for a given Item category. There are two types of attributes: 

*  attributes are  included in every category.

*  attributes are defined by an Account Admin in a workspace. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| includePossibleValues | true or false | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false. |
| creatableOnly | true or false | If this is set to true, it returns only creatable attributes, which are settable during creation of an item. |
| editableOnly | true or false | If this is set to true, it returns only editable attributes, which are settable during update of an item. The default value is false. |
| searchableOnly | true or false | If this is set to true, it returns only searchable attributes, which are searchable when getting items. |

If this is set to false, it returns only non\-creatable attributes.

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Headers

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
GET all attributes for a given category with possible values included



/settings/items/categories/&lt;GUID&gt;/attributes?includePossibleValues=true

```
{
    "count": 31,
    "results": [
        {
            "active": true,
            "allowsExplicitNullValue": true,
            "apiName": "M4O7Q3OF25M4N6NM8LYP",
            "creatable": true,
            "custom": true,
            "deleted": false,
            "editable": true,
            "fieldType": "SINGLE_LINE_TEXT",
            "global": false,
            "guid": "M4O7Q3OF25M4N6NM8LYP",
            "maxLength": 1000,
            "name": "Material",
            "origin": {
                "guid": "5N7Q9M7YLO7H0JY556SY",
                "name": "Fabricated Plastic"
            },
            "required": false,
            "revisionControlled": true,
            "searchable": true,
            "visibleWhenBlank": false
        },
        {
            "active": true,
            "allowsExplicitNullValue": true,
            "apiName": "ZH1K3G1SFIZH0JY14JDN",
            "creatable": true,
            "custom": true,
            "defaultValue": "No",
            "deleted": false,
            "editable": true,
            "example": "Yes/No",
            "fieldType": "FIXED_DROP_DOWN",
            "global": true,
            "guid": "ZH1K3G1SFIZH0JY14JDN",
            "multiSelect": false,
            "name": "Orderable",
            "origin": {
                "guid": "2K4N6J4VIL4EXGV223NP",
                "name": "-uncategorized-"
            },
            "possibleValues": [
                "Yes",
                "No",
                "N/A"
            ],
            "required": false,
            "revisionControlled": true,
            "searchable": true,
            "visibleWhenBlank": false
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
            "guid": "7P9SBO90NQ8VEXGZI1KH",
            "inViews": [
                "ITEM_SPECS"
            ],
            "name": "Category",
            "origin": {
                "guid": "2K4N6J4VIL4EXGV223NP",
                "name": "-uncategorized-"
            },
            "required": false,
            "searchable": true
        },
        ...
      }
    ]
}       
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
