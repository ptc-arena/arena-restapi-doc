# GET Quality Processes Search
/qualityprocesses

Returns a collection of Quality Process objects matching the given search criteria. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all quality processes where results should begin. All processes before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of quality processes is 20. Can return up 400 suppliers.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| \[additional attribute guid value\]<br> | string<br> | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN \(where multi-select is true\). See note below this table for additional details.<br>Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy-mm-dd. In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019:<br>GET /qualityprocesses?GYI16WXX6DUDWFYHPRY3=2019-04-01<br> |
| description<br> | string<br> | Quality process description<br> |
| number<br> | string<br> | quality process number<br> |
| name<br> | string<br> | quality process name<br> |
| template.guid<br> | string<br> | template unique identifier<br> |
| type<br> | string<br> | quality process type<br> |
| owner.fullName<br> | string<br> | owner full name \(first and last\)<br> |
| owner.guid<br> | string<br> | owner unique ID<br> |
| status<br> | string<br> | status of the quality process \(OPEN, IN_PROGRESS, COMPLETED\). Uncompleted Quality Processes can be queried by inputting a NOT operator, represented by an exclamation point, with status. Example: url/qualityprocesses?status=!COMPLETED<br> |
| creator.fullName<br> | string<br> | creator full name \(first and last\)<br> |
| creator.guid<br> | string<br> | creator unique ID<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

Uncompleted Quality Processes can be queried by using the search attribute status equal to !Completed. Example URL: .../qualityprocesses?status=!COMPLETED

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi-colon.

When using a semi-colon to separate values in a FIXED_DROP_DOWN search, note that the semi-colon will always act as an OR. This is relevant when performing a Multi-Select search.

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all quality processes

/qualityprocesses

```
{  
   "count":9,
   "results":[  
      {  
         "completedDateTime":null,
         "creationDateTime":"2016-04-19T19:41:32Z",
         "creator":{  
            "fullName":"Roy S",
            "guid":"7P9SXNOOX4L4N6P8BG6R"
         },
         "currentStep":{  
            "approvals":null,
            "attributes":null,
            "guid":"YG0JOEFFOVEATCVEUGI5"
         },
         "description":"New Quality Process",
         "guid":"XFZINDEENUD9SBUDTFH4",
         "name":"New Process Introduction",
         "number":"8D-000003",
         "owner":{  
            "fullName":"Roy Stafford",
            "guid":"GYI16WXX6DUDWFYHPRY3"
         },
         "status":"OPEN",
         "statusMode":"AUTOMATIC",
         "targetCompletionDateTime":null,
         "template":{  
            "active":null,
            "guid":"6O8RWMNNW3MI1K3M2TOK"
         },
         "type":"Design"
      },
      ...
   ]
}
```
Returns an error if a parameter is not a valid search attribute.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3019,
      "message": "The attribute \"a\" is not searchable."
    }
  ]
}
```
