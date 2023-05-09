# GET Supplier Items


/supplieritems

Returns an array of  objects matching the given search criteria.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all supplier items where results should begin. All supplier items before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. By default the maximum number of supplier items is 20. Can return up 400 supplier items. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| \[additional attribute guid value\] | string | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN. See note below this table for additional details. |
| name | string | supplier item name |
| number | true or false | supplier item number |
| supplier.name | string | supplier name |
| supplier.guid | string | supplier unique identifier |

Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd.

In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019: 

GET /supplieritems?HZJ2LT22ZGZ5O7QY77YO=2019\-04\-01

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
Get all supplier items where the name includes "capacitor"



/supplieritems?name=\*capacitor

```
{
   "count":20,
   "results":[
      {
         "creationDateTime":"2011-02-11T17:13:08Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "description":null,
         "guid":"GYI1KS11YFY3M5OVMVS1",
         "name":"Capacitor; Ceramic",
         "number":"CC1206KKX7R7BB10",
         "offTheShelf":true,
         "supplier":{
            "guid":"K2M5OW552J28RAT1AA1X"
         },
         "type":"PART",
         "uom":"each"
      },
      {
         "creationDateTime":"2011-02-11T17:13:09Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker"
         },
         "description":null,
         "guid":"ASCVEMVVS9SXGZIPGPK7",
         "name":"Capacitor; Ceramic",
         "number":"NMC0603X7R103K50TRPF",
         "offTheShelf":true,
         "supplier":{
            "guid":"HZJ2LT22ZGZ5O7QY77YO"
         },
         "type":"PART",
         "uom":"each"
      },
      ...
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
