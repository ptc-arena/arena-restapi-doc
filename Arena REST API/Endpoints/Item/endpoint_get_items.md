# GET Items (Search)


/items

Returns a collection of  objects matching the given search criteria.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all items where results should begin. All items before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up to 400 compact items. |
| criteria | url encoded string | The criteria search parameter uses the same criteria format used in API Item Exports. Passing this criteria through a query string requires url encoding of the characters. For additional information See .  |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| \[additional attribute guid value\] | string | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN, FIXED_DROPDOWN, & FIXED_DROPDOWN \(where multi\-select is true\). See note below this table for additional details. |
| assemblyType | String | Possible values include: TOP_LEVEL_ASSEMBLY; ASSEMBLY; NOT_AN_ASSEMBLY |
| category.guid | string | category unique ID |
| creator.fullName | string | the full name \(first and last\) of the creator of the item  |
| creator.guid | string | creator unique ID |
| name | string | item name |
| number | string | item number |
| revisionNumber | string | revision number |
| description | string | item description |
| owner.fullName | string | item owner full name |
| effectiveDateTimeFrom | Date\-Formatted String | the date and time \(in Zulu format\) the effective revision of an item was made effective |
| effectiveDateTimeTo | Date\-Formatted String | the date and time \(in Zulu format\) a revision of an item was superseded  |
| inAssembly | true or false | true indicates an item is included in at least one assembly \(appears on a BOM\) |
| lifecyclePhase.guid | string | lifecyclePhase unique ID |
| modifiedBom | true or false | true indicates the BOM of the item includes modifications to the working revision |
| modifiedFiles | true or false | true indicates the Files view of the item includes modifications to the working revision |
| modifiedSourcing | true or false | true indicates the Sourcing view of the item includes modifications to the working revision |
| modifiedSpecs | true or false | true indicates the Specs view of the item includes modifications to the working revision |

Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd.

In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019: 

GET /items?4M6PUJNPNM3L4N25ZZ5F=2019\-04\-01

Top level assemblies are items that contain assemblies but themselves are not included as items in another item's assembly.

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi\-colon.

When using a semi\-colon to separate values in a FIXED_DROP_DOWN search, note that the semi\-colon will always act as an OR. This is relevant when performing a Multi\-Select search.

For example with FIXED_DROP_DOWN, multiselect = True: GET /Items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN contains Option 1 OR Option 2 \(or both\). On the other hand FIXED_DROP_DOWN, multiselect=False: GET /items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN equals Option 1 OR Option 2.

Search in Zulu format is supported for custom attribute field type Date.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all items



GET /items

```
{  
   "count":20,
   "results":[  
      {  
         "assemblyType": "ASSEMBLY",
         "category":{  
            "guid":"5N6P8RAK3MY6UNTA"
         },
         "creationDateTime":"2011-06-02T19:23:31Z",
         "guid":"VDXGLBCCLSBSBQMM0SJU",
         "inAssembly": true,
         "lifecyclePhase":{  
            "guid":"7G6P3WAD3MG6GNFD",
            "name":"In Production"
         },
         "name":"PCBA, EveryRoad, Model 300",
         "number":"830-00001",
         "revisionNumber":"D",
         "url": {
                "api": "https://api.arenasolutions.com/v1/items/VDXGLBCCLSBSBQMM0SJU",
                "app": "https://app.bom.com/VDXGLBCCLSBSBQMM0SJU"
      },
      ...
      ]
}
```
Get items with owner "James Deckard" and in category "Subassembly"



GET &lt;url&gt;/items?owner.fullName=James Deckard&category.guid=UCWFKABBKRAK3MY6UNTU

```
{  
   "count":4,
   "results":[  
      {  
         "assemblyType": "ASSEMBLY",
         "category":{  
            "guid":"ZH1K3K3JFSBL4N6O1ZQS"
         },
         "creationDateTime":"2011-02-11T16:52:40Z",
         "guid":"FXH0J0JZV8R8RASMLCR5",
         "inAssembly": true,
         "lifecyclePhase":{  
            "guid":"FXH0J0JZV8QTCVEXGZM5",
            "name":"In Production"
         },
         "name":"Subassembly, EveryRoad, Front Bezel",
         "number":"090-0001",
         "revisionNumber":"A",
         "url": {
                "api": "https://api.arenasolutions.com/v1/items/FXH0J0JZV8R8RASMLCR5",
                "app": "https://app.bom.com/FXH0J0JZV8R8RASMLCR5"
      },
      {  
         "assemblyType": "NOT_AN_ASSEMBLY",
         "category":{  
            "guid":"ZH1K3K3JFSBL4N6O1ZQS"
         },
         "creationDateTime":"2011-02-11T16:52:40Z",
         "guid":"VDXGZGZFBO7O7Q821S54",
         "inAssembly": true,
         "lifecyclePhase":{  
            "guid":"FXH0J0JZV8QTCVEXGZM5",
            "name":"In Production"
      },
         "name":"Documentation Package, Everyroad Model 300/500",
         "number":"090-0003",
         "revisionNumber":"A",
         "url": {
                "api": "https://api.arenasolutions.com/v1/items/VDXGZGZFBO7O7Q821S54",
                "app": "https://app.bom.com/VDXGZGZFBO7O7Q821S54" 
      },
      ...
   ]
}
```
Get effective revisions of items  where the revisions were made effective between 4pm February 11, 2013 and 4pm March 11, 2013.



GET /items?effectiveDateTimeFrom=2013\-02\-11T16:00:00Z&effectiveDateTimeTo=2013\-03\-11T16:00:00Z

```
{  
   "count":2,
   "results":[  
      {  
         "assemblyType": "ASSEMBLY",
         "category":{  
            "guid":"N5P8R8R73GZ9SBUCNG61"
         },
         "creationDateTime":"2011-02-11T16:52:40Z",
         "guid":"GYI1K1K0W9S9SBSLE716",
         "inAssembly": true,
         "lifecyclePhase":{  
            "guid":"0I2L4L4KGTBEXGZI1H01",
            "name":"Design Verification"
         },
         "name":"Circuit Board, EveryRoad, Model 500",
         "number":"040-0002",
         "revisionNumber":"2",
         "url": {
                "api": "https://api.arenasolutions.com/v1/items/GYI1K1K0W9S9SBSLE716",
                "app": "https://app.bom.com/GYI1K1K0W9S9SBSLE716"
      },
      {  
         "assemblyType": "ASSEMBLY",
         "category":{  
            "guid":"ZH1K3K3JFSBL4N6O1ZQS"
         },
         "creationDateTime":"2011-02-11T16:52:40Z",
         "guid":"1J3M5M5LHUDUDWE86ARW",
         "inAssembly": true,
         "lifecyclePhase":{  
            "guid":"EWGZIZIYU7PSBUDWFV6U",
            "name":"Eng Verification"
         },
         "name":"Subassembly, Connector, Stormwatch",
         "number":"090-0006",
         "revisionNumber":"3",
         "url": {
                "api": "https://api.arenasolutions.com/v1/items/1J3M5M5LHUDUDWE86ARW",
                "app": "https://app.bom.com/1J3M5M5LHUDUDWE86ARW"
         }
      }
   ]
}
```
Request with an invalid search attribute.

GET /items?owner.Name=\*Walker

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3019,
         "message":"The attribute \"owner.Name\" is not searchable."
      }
   ]
}
```
