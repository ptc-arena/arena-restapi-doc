# Quality Affected

| Field | Data Type | Description |
|  --- |  --- |  --- | 
| description | String | description of the URL. This field is included when Type=URL |
| display | String | Test string displayed within the application for this URL. This field is included when Type=URL. |
| guid | String | The unique identifier for the affected object. This field is included when Type=ITEM, QUALITY, or REQUEST. |
| link | String | Internet address for this URL. This field is included when Type=URL. |
| step | Reference | The specific step of the affected quality process that is associated with this quality process step. This field is included when Type=QUALITY. |
| type | String | The type of object associated with this quality process step. Values can be ITEM, CHANGE, SUPPLIER, SUPPLIER ITEM, FILE, QUALITY, or URL. |

