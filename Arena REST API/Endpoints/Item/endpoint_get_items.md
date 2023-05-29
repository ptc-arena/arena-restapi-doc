# GET Items (Search)


/items

Returns a collection of  objects matching the given search criteria.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all items where results should begin. All items before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up to 400 compact items.<br> |
| criteria<br> | url encoded string<br> | The criteria search parameter uses the same criteria format used in API Item Exports. Passing this criteria through a query string requires url encoding of the characters. For additional information See .<br>GET Items \(Search\) Criteria Parameter<br> |
| responseview<br> | string<br> | Allows users to customize the scope and size of the response data. Possible values and definitions:<br> <br> * minimum \- returns the GUID, item number, and url.<br><br> * compact \- returns the commen set of data that includes some core attrinutes in addition to the attributes returned in the minimum response.<br><br> * full \- returns the complete set of data including custom attributes.<br> |

* minimum \- returns the GUID, item number, and url.

* compact \- returns the commen set of data that includes some core attrinutes in addition to the attributes returned in the minimum response.

* full \- returns the complete set of data including custom attributes.

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| \[additional attribute guid value\]<br> | string<br> | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN, FIXED_DROPDOWN, & FIXED_DROPDOWN \(where multi\-select is true\). See note below this table for additional details.<br>Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd. In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019:<br>GET /items?4M6PUJNPNM3L4N25ZZ5F=2019\-04\-01<br> |
| assemblyType<br> | String<br> | Possible values include: TOP_LEVEL_ASSEMBLY; ASSEMBLY; NOT_AN_ASSEMBLY<br>Top level assemblies are items that contain assemblies but themselves are not included as items in another item's assembly.<br> |
| category.guid<br> | string<br> | category unique ID<br> |
| creator.fullName<br> | string<br> | the full name \(first and last\) of the creator of the item<br> |
| creator.guid<br> | string<br> | creator unique ID<br> |
| name<br> | string<br> | item name<br> |
| number<br> | string<br> | item number<br> |
| revisionNumber<br> | string<br> | revision number<br> |
| description<br> | string<br> | item description<br> |
| owner.fullName<br> | string<br> | item owner full name<br> |
| effectiveDateTimeFrom<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) the effective revision of an item was made effective<br> |
| effectiveDateTimeTo<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a revision of an item was superseded<br> |
| inAssembly<br> | true or false<br> | true indicates an item is included in at least one assembly \(appears on a BOM\)<br> |
| lifecyclePhase.guid<br> | string<br> | lifecyclePhase unique ID<br> |
| modifiedBom<br> | true or false<br> | true indicates the BOM of the item includes modifications to the working revision<br> |
| modifiedFiles<br> | true or false<br> | true indicates the Files view of the item includes modifications to the working revision<br> |
| modifiedSourcing<br> | true or false<br> | true indicates the Sourcing view of the item includes modifications to the working revision<br> |
| modifiedSpecs<br> | true or false<br> | true indicates the Specs view of the item includes modifications to the working revision<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi\-colon.

When using a semi\-colon to separate values in a FIXED_DROP_DOWN search, note that the semi\-colon will always act as an OR. This is relevant when performing a Multi\-Select search.

For example with FIXED_DROP_DOWN, multiselect = True: GET /Items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN contains Option 1 OR Option 2 \(or both\). On the other hand FIXED_DROP_DOWN, multiselect=False: GET /items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN equals Option 1 OR Option 2.

Search in Zulu format is supported for custom attribute field type Date.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
