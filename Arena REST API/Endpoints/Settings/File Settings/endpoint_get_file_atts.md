# GET File Attributes
/settings/files/attributes

Returns  Attributes available for Files. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| includePossibleValues<br> | true or false<br> | If this is set to true, it returns all the possible values for Drop Down List attributes. The default value is false.<br> |
| creatableOnly<br> | true or false<br> | If this is set to true, it returns only creatable attributes, which are settable during creation of a file.<br>If this is set to false, it returns only non-creatable attributes.<br> |
| editableOnly<br> | true or false<br> | If this is set to true, it returns only editable attributes, which are settable during update of a file. The default value is false.<br> |
| searchableOnly<br> | true or false<br> | If this is set to true, it returns only searchable attributes, which are searchable when getting files.<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all file attributes with possible values included

GET /settings/files/attributes?includePossibleValues=true

```
{  
   "count":38,
   "results":[  
      {  
         "allowsExplicitNullValue":false,
         "apiName":"author",
         "creatable":true,
         "editable":true,
         "fieldType":"OBJECT",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "required":true,
         "searchable":true
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"category",
         "creatable":true,
         "editable":true,
         "fieldType":"OBJECT",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "required":true,
         "searchable":true
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"creationDateTime",
         "creatable":false,
         "editable":false,
         "fieldType":"DATETIME",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "searchable":true
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"description",
         "creatable":true,
         "editable":true,
         "fieldType":"SINGLE_LINE_TEXT",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "maxLength":4000,
         "required":false,
         "searchable":true
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"format",
         "creatable":true,
         "editable":true,
         "fieldType":"DROP_DOWN",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "maxLength":100,
         "required":false,
         "searchable":true
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"guid",
         "creatable":false,
         "editable":false,
         "fieldType":"GUID",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "searchable":false
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"storageMethod",
         "creatable":true,
         "deprecated":true,
         "developerNotes":"This attribute is deprecated and storageMethodName must be used instead",
         "editable":false,
         "fieldType":"INTEGER",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "required":true,
         "searchable":false
      },
      {  
         "allowsExplicitNullValue":false,
         "apiName":"storageMethodName",
         "creatable":true,
         "editable":false,
         "fieldType":"FIXED_DROP_DOWN",
         "inViews":[  
            "ITEM_FILES",
            "FILE_SUMMARY",
            "SI_FILES"
         ],
         "required":true,
         "searchable":false
      },
      …
   ]
}
```
