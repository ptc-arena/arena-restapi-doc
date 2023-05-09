# GET Suppliers


/suppliers

Returns a collection of  objects matching the given search criteria.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all suppliers where results should begin. All suppliers before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. By default the maximum number of suppliers is 20. Can return up 400 suppliers. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| \[additional attribute guid value\] | string | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN. See note below this table for additional details. |
| name | string | supplier name |
| supplierId | string | The unique identifier of a supplier in the Arena database |

Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd.

In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019: 

GET /suppliers?UCWFY6FFCTCI1K3B82OC=2019\-04\-01


Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi\-colon.

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
Get all suppliers whose name includes the string "board"



/suppliers?name=\*board

```
{
   "count":2,
   "results":[
      {
         "accountNumber":null,
         "addresses":null,
         "approvalStatus":"unrated",
         "creationDateTime":"2011-02-11T17:13:07Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "description":"Full service board supplier",
         "guid":"YG0J2AJJGXGM5O7FOOG1",
         "name":"Adaptive Circuit Boards",
         "phoneNumbers":null,
         "supplierId":"Adaptive",
         "website":"www.zombo.com"
      },
      {
         "accountNumber":"1",
         "addresses":null,
         "approvalStatus":"approved",
         "creationDateTime":"2018-04-27T00:18:52Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "description":"Board house",
         "guid":"UCWFY6FFCTCI1K3B82OC",
         "name":"The Board Room",
         "phoneNumbers":null,
         "supplierId":"theboardroominc,
         "website":"www.zombo.com"
      }
   ]
}
```
