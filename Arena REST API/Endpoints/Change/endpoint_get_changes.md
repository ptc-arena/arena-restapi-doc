# GET Changes


/changes

Returns a collection of  objects matching the given search criteria. Note that the Changes returned here are a compact version. For a full Change object, use the GET Change endpoint GET/changes/guid.

Changes include different attributes depending on the effectivityType \(PERMANENT_ON_APPROVAL, PERMANENT_ON_DATE, or TEMPORARY\) and lifecyclePhase \(OPEN_AND_UNLOCKED, OPEN_AND_LOCKED, SUBMITTED_FOR_ROUTING, SUBMITTED_FOR_APPROVAL, REJECTED, CANCELED, APPROVED, EFFECTIVE, COMPLETED, or EXPIRED\)

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all changes where results should begin. All changes before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up 400 changes.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| \[additional attribute guid value\]<br> | string<br> | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN \(where multi\-select is true\). See note below this table for additional details.<br>Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd. In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019:<br>GET /changes?9QU24KGNKOUGD1Z0RM3X=2019\-04\-01<br> |
| category.guid<br> | string<br> | category unique ID<br> |
| creator.guid<br> | string<br> | creator user unique ID<br> |
| effectiveDateTimeFrom<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a change was made effective. Returns all Changes made effective after this date.<br> |
| effectiveDateTimeTo<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a change was made effective. Returns all Changes made effective before this date.<br> |
| implementationStatus<br> | string<br> | implementation status of the change. Values can be , , , or .<br>NOT_STARTED<br>IN_PROGRESS<br>NEEDS_ATTENTION<br>DONE<br> |
| expirationDateTimeFrom<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a change is set to expire. Returns all Changes that expire after this date.<br> |
| expirationDateTimeTo<br> | Date\-Formatted String<br> | the date and time \(in Zulu format\) a change is set to expire. Returns all Changes that expire before this date.<br> |
| lifecycleStatus.type<br> | string<br> | lifecycle status of the change. Values can be , , , , , , , , , or .<br>OPEN_AND_UNLOCKED<br>OPEN_AND_LOCKED<br>SUBMITTED_FOR_ROUTING<br>SUBMITTED_FOR_APPROVAL<br>REJECTED<br>CANCELED<br>APPROVED<br>EFFECTIVE<br>COMPLETED<br>EXPIRED<br> |
| number<br> | string<br> | number of the change<br> |
| title<br> | string<br> | title of the change<br> |

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
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all changes



GET /changes

```
{
   "count":25,
   "results":[
      {
         "category":{
            "guid":"ASCVERC3QTCM5O3AABZF"
         },
         "creationDateTime":"2013-12-11T19:33:12Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":"2013-12-11T19:41:13Z",
         "guid":"7P9SBO90NQ9CVDTX9JUN",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2013-12-11T19:41:13Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"DCO-000003",
         "submissionDateTime":"2013-12-11T19:38:10Z",
         "title":"Release new rev of discretes to include CoCs"
      },
      {
         "category":{
            "guid":"4M6P8L6XKN6GZIX445T6"
         },
         "creationDateTime":"2018-03-07T00:53:59Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":null,
         "expirationDateTime":"2018-03-30T07:00:00Z",
         "guid":"3L5O7K5WJM58R9PPUQJC",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2018-03-07T00:53:59Z",
         "lifecycleStatus":{
            "type":"OPEN_AND_UNLOCKED"
         },
         "number":"DEV-000002",
         "submissionDateTime":null,
         "title":"Use Alternate Chipset with New Logic in 500 Boards"
      },
      {
         "category":{
            "guid":"7P9SBO90NQ9J2L0778WO"
         },
         "creationDateTime":"2015-02-18T21:56:44Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":null,
         "guid":"6O8RAN8ZMP8BUCSWLSDB",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2016-07-18T21:19:06Z",
         "lifecycleStatus":{
            "type":"SUBMITTED_FOR_APPROVAL"
         },
         "number":"ECO-000017",
         "submissionDateTime":"2016-07-18T21:18:39Z",
         "title":"Switch resistor combination in 830-00001"
      },
      {
         "category":{
            "guid":"ASCVERC3QTCM5O3AABZF"
         },
         "creationDateTime":"2012-01-11T19:14:23Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":"2012-01-11T19:16:35Z",
         "guid":"L3N6P2NE14NQ9SEDI1DJ",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2012-01-11T19:16:35Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"DCO-000002",
         "submissionDateTime":"2012-01-11T19:14:46Z",
         "title":"BOM correction - Docs only"
      },
      {
         "category":{
            "guid":"BTDWFSD4RUDN6P4BBC0T"
         },
         "creationDateTime":"2012-04-27T22:34:15Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":"2012-04-27T23:16:20Z",
         "guid":"HZJ2LYJAX0JM5N384TAO",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2012-04-27T23:16:20Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"MCO-000003",
         "submissionDateTime":"2012-04-27T22:34:47Z",
         "title":"Add Trilby Technology as Source for 830-00001"
      },
      {
         "category":{
            "guid":"7P9SBO90NQ9J2L0778WO"
         },
         "creationDateTime":"2018-03-07T01:17:44Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":null,
         "guid":"5N7Q9M7YLO7ATBRRWSLF",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2018-03-07T01:21:34Z",
         "lifecycleStatus":{
            "type":"SUBMITTED_FOR_APPROVAL"
         },
         "number":"ECO-000022",
         "submissionDateTime":"2018-03-07T01:21:20Z",
         "title":"New Fabrication for Everyroad Rear Panel"
      },
      {
         "category":{
            "guid":"BTDWFSD4RUDN6P4BBC0T"
         },
         "creationDateTime":"2012-01-11T00:49:46Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"WEYH0DYPCFWFYH0JSIPD"
         },
         "effectiveDateTime":"2012-01-12T23:55:53Z",
         "guid":"M4O7Q3OF25ORATFGURLY",
         "implementationStatus":"NOT_STARTED",
         "lifecycleDateTime":"2012-01-12T23:55:53Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"MCO-000002",
         "submissionDateTime":"2012-01-11T00:50:00Z",
         "title":"Add Plasmus Plastics as Source for Everyroad Front Bezel 432-00001"
      },
      ...
   ]
}
```
Get effective  changes in category ECO



GET &lt;url&gt;/changes?lifecycleStatus.type=effective&category.guid=L3N6PX663K3DWFYF3F6C

```
{
   "count":5,
   "results":[
      {
         "category":{
            "guid":"L3N6PX663K3DWFYF3F6C"
         },
         "creationDateTime":"2011-02-14T23:38:11Z",
         "creator":{
            "email":"rborger@everyroadgps.com",
            "fullName":"Rachael Borger",
            "guid":"9RBUDLUUR8P8RATCVROR"
         },
         "effectiveDateTime":"2011-02-15T00:11:43Z",
         "guid":"K2M5OW552J25O6PARG53",
         "implementationStatus":"IN_PROGRESS",
         "lifecycleDateTime":"2011-02-15T00:11:43Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"ECO-000002",
         "submissionDateTime":"2011-02-15T00:05:03Z",
         "title":"Production Release of EveryRoad GPS PCBA and components"
      },
      {
         "category":{
            "guid":"L3N6PX663K3DWFYF3F6C"
         },
         "creationDateTime":"2011-02-15T01:33:35Z",
         "creator":{
            "email":"tmakamuri@everyroadgps.com",
            "fullName":"Toshiro Makamuri",
            "guid":"CUEXGOXXUBSBUDWFYURL"
         },
         "effectiveDateTime":"2011-02-15T21:22:57Z",
         "guid":"L3N6PX663K36P7QBSH62",
         "implementationStatus":"IN_PROGRESS",
         "lifecycleDateTime":"2011-02-15T21:22:57Z",
         "lifecycleStatus":{
            "type":"EFFECTIVE"
         },
         "number":"ECO-000005",
         "submissionDateTime":"2011-02-15T19:30:12Z",
         "title":"Production Release of Everyroad GPS Custom Mechanical Parts"
      },
      ...
   ]
}
```
