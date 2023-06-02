# GET Quality Processes Search
/qualityprocesses

Returns a collection of Quality Process objects matching the given search criteria. 

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all quality processes where results should begin. All processes before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. By default the maximum number of quality processes is 20. Can return up 400 suppliers.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| \[additional attribute guid value\]  | string  |  This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN \(where multi-select is true\). See note below this table for additional details.Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy-mm-dd.<br><br>In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019: <br> GET /qualityprocesses?GYI16WXX6DUDWFYHPRY3=2019-04-01<br>   |
| description  | string  | Quality process description  |
| number  | string  | quality process number  |
| name  | string  | quality process name  |
| template.guid  | string  | template unique identifier  |
| type  | string  | quality process type  |
| owner.fullName  | string  | owner full name \(first and last\)  |
| owner.guid  | string  | owner unique ID  |
| status  | string  | status of the quality process \(OPEN, IN_PROGRESS, COMPLETED\). Uncompleted Quality Processes can be queried by inputting a NOT operator, represented by an exclamation point, with status. Example: url/qualityprocesses?status=!COMPLETED  |
| creator.fullName  | string  | creator full name \(first and last\)  |
| creator.guid  | string  | creator unique ID  |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

Uncompleted Quality Processes can be queried by using the search attribute status equal to !Completed. Example URL: .../qualityprocesses?status=!COMPLETED

For additional attribute field type MULTI_LINE_TEXT searches, different values can be  separated with an asterisk.

For additional attribute field types DROP_DOWN & FIXED_DROP_DOWN searches, different values can be separated with a semi-colon.

When using a semi-colon to separate values in a FIXED_DROP_DOWN search, note that the semi-colon will always act as an OR. This is relevant when performing a Multi-Select search.

For example with FIXED_DROP_DOWN, multiselect = True: GET /Items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN contains Option 1 OR Option 2 \(or both\). On the other hand FIXED_DROP_DOWN, multiselect=False: GET /items?J1L49Y281EVDWFUXRSCZ=Option 1;Option 2 will return all Items where the FIXED_DROP_DOWN equals Option 1 OR Option 2.

Search in Zulu format is supported for custom attribute field type Date.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results. Similarly, the plus character, \+, can be encoded as %2b in order to return results.

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
