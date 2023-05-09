# GET Requests


/requests

Returns a collection of  Requests objects matching the given search criteria. Note that the Requests returned here are a compact version. For a full Request object, use the GET Request endpoint GET/requests/guid.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| offset | integer | Specifies the position in the list of all changes where results should begin. All changes before the offset in the search results are ignored. The default value is 0. |
| limit | integer | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up 400 changes. |

## Searchable Attributes

| Name | Value | Description |
|  --- |  --- |  --- | 
| \[additional attribute guid value\] | string | This special search permits searching for strings in additional attribute values. For example GET /items?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN \(where multi\-select is true\). See note below this table for additional details. |
| category.guid | string | category unique ID |
| creator.guid | string | creator user unique ID |
| deferralCode | string | Denotes the nature of a deferred Request. Values can be customized within Workspace Settings. |
| lifecycleStatus.type | string | lifecycle status of the request. Values can be , , , , or  |
| number | string | number of the request |
| requestCode | string | Denotes the nature of the request. Set at Request creation. Possible values can be customized within Workspace Settings. |
| resolutionCode | string | Denotes the nature of a Promoted or Closed Request. Values can be customized within Workspace Settings. |
| submissionDateTimeFrom | Date\-Formatted String | the date and time \(in Zulu format\) a request is submitted. Returns all Requests that are submitted after this date. |
| submissionDateTimeTo | Date\-Formatted String | the date and time \(in Zulu format\) a request was submitted. Returns all Requests submitted before this date. |
| title | string | title of the Request. |

Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy\-mm\-dd.

In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019: 

GET /requests?4M6PUJNPNM3L4N25ZZ5F=2019\-04\-01

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all Requests



GET /requests

```
{
    "count": 9,
    "results": [
        {
            "category": {
                "guid": "I0K3MZKBY1KUDWBIIJ7C",
                "name": "Manufacturing Change Request"
            },
            "creationDateTime": "2011-07-11T19:52:59Z",
            "creator": {
                "email": "ykeller@arenasolutions.com",
                "fullName": "Yvette Keller",
                "guid": "VDXGZCXOBEVEXGZIWZJK"
            },
            "deferDeadlineDateTime": null,
            "deferralCode": null,
            "evaluatorGroup": {
                "guid": "3L5O7K5WJM3K3M5O5JDC",
                "name": "Product Enhancement"
            },
            "guid": "N5P8R4PG36PO7QXI618R",
            "lifecycleDateTime": "2011-07-11T19:52:59Z",
            "lifecycleStatus": {
                "type": "UNSUBMITTED"
            },
            "number": "MCR-000001",
            "problem": "In manufacturing we are finding that the phillips pan head screws on the EveryRoad GPS Model 300 are not holding the screw driver bits very well. We are using pneumatic screw drivers and they are disengaging as we assemble the product. The sudden jumps and slips are sometimes leaving track marks on the plastic shells.",
            "requestCode": "Manufacturability",
            "requestedAction": "Please change the screws in the EveryRoad GPS from a phillips head drive style to a torx head drive style. Torx provides better engagement and will make it easier to assembled the product.",
            "resolutionCode": null,
            "submissionDateTime": null,
            "submitter": null,
            "title": "Change drive style for EveryRoad screws from Phillips to Torx"
        },
        {
            "category": {
                "guid": "HZJ2LYJAX0JTCVAHHI66",
                "name": "Engineering Change Request"
            },
            "creationDateTime": "2011-07-11T23:28:57Z",
            "creator": {
                "email": "ykeller@arenasolutions.com",
                "fullName": "Yvette Keller",
                "guid": "VDXGZCXOBEVEXGZIWZJK"
            },
            "deferDeadlineDateTime": null,
            "deferralCode": null,
            "evaluatorGroup": {
                "guid": "4M6P8L6XKN4L4N6P7X7E",
                "name": "Engineering plus Board Supplier"
            },
            "guid": "O6Q9S5QH47QP8RYJ729F",
            "lifecycleDateTime": "2011-08-09T22:32:56Z",
            "lifecycleStatus": {
                "type": "PROMOTED"
            },
            "number": "ECR-000002",
            "problem": "We've had some reports of EveryRoad 300's rear panel melting and in one case, a probable fire. All melting situations have occurred on vehicle dashboards. Because of the risk of lawsuits associated with this problem, we are ranking it as high-urgency.",
            "requestCode": "Performance",
            "requestedAction": "Engineering should begin thermal testing / analysis immediately to determine what might be causing this problem.",
            "resolutionCode": "Approved [Immediate]",
            "submissionDateTime": "2011-08-04T20:25:47Z",
            "submitter": {
                "email": "jparker@everyroadgps.com",
                "fullName": "John Parker",
                "guid": "XFZI1EZQDGXGZI1KTJQ2"
            },
            "title": "EveryRoad Model 300 Case Melting"
        },
        {
            "category": {
                "guid": "I0K3MZKBY1KUDWBIIJ7C",
                "name": "Manufacturing Change Request"
            },
            "creationDateTime": "2011-07-11T20:01:22Z",
            "creator": {
                "email": "ykeller@arenasolutions.com",
                "fullName": "Yvette Keller",
                "guid": "VDXGZCXOBEVEXGZIWZJK"
            },
            "deferDeadlineDateTime": null,
            "deferralCode": null,
            "evaluatorGroup": null,
            "guid": "P7RAT6RI58RQ9SZK83AX",
            "lifecycleDateTime": "2011-07-11T20:01:22Z",
            "lifecycleStatus": {
                "type": "UNSUBMITTED"
            },
            "number": "MCR-000002",
            "problem": "The model 300 seems to show fingerprints on the enclosure. The problem, while not affecting performance, is visually ugly. Can anything be done?",
            "requestCode": "Performance",
            "requestedAction": "Please investigate new materials or textures for the EveryRoad housing.",
            "resolutionCode": null,
            "submissionDateTime": null,
            "submitter": null,
            "title": "Fingerprints show readily on the EveryRoad housing"
        },
        ...
    ]
}
```
Get promoted  changes in category Engineering Change Request.



GET &lt;url&gt;/requests?lifecycleStatus.type=PROMOTED&category.guid=HZJ2LYJAX0JTCVAHHI66

```
{
    "count": 2,
    "results": [
        {
            "category": {
                "guid": "HZJ2LYJAX0JTCVAHHI66",
                "name": "Engineering Change Request"
            },
            "creationDateTime": "2011-07-11T23:28:57Z",
            "creator": {
                "email": "ykeller@arenasolutions.com",
                "fullName": "Yvette Keller",
                "guid": "VDXGZCXOBEVEXGZIWZJK"
            },
            "deferDeadlineDateTime": null,
            "deferralCode": null,
            "evaluatorGroup": {
                "guid": "4M6P8L6XKN4L4N6P7X7E",
                "name": "Engineering plus Board Supplier"
            },
            "guid": "O6Q9S5QH47QP8RYJ729F",
            "lifecycleDateTime": "2011-08-09T22:32:56Z",
            "lifecycleStatus": {
                "type": "PROMOTED"
            },
            "number": "ECR-000002",
            "problem": "We've had some reports of EveryRoad 300's rear panel melting and in one case, a probable fire. All melting situations have occurred on vehicle dashboards. Because of the risk of lawsuits associated with this problem, we are ranking it as high-urgency.",
            "requestCode": "Performance",
            "requestedAction": "Engineering should begin thermal testing / analysis immediately to determine what might be causing this problem.",
            "resolutionCode": "Approved [Immediate]",
            "submissionDateTime": "2011-08-04T20:25:47Z",
            "submitter": {
                "email": "jparker@everyroadgps.com",
                "fullName": "John Parker",
                "guid": "XFZI1EZQDGXGZI1KTJQ2"
            },
            "title": "EveryRoad Model 300 Case Melting"
        },
        {
            "category": {
                "guid": "HZJ2LYJAX0JTCVAHHI66",
                "name": "Engineering Change Request"
            },
            "creationDateTime": "2011-07-11T22:55:16Z",
            "creator": {
                "email": "ykeller@arenasolutions.com",
                "fullName": "Yvette Keller",
                "guid": "VDXGZCXOBEVEXGZIWZJK"
            },
            "deferDeadlineDateTime": null,
            "deferralCode": null,
            "evaluatorGroup": {
                "guid": "3L5O7K5WJM3K3M5O5JDC",
                "name": "Product Enhancement"
            },
            "guid": "Q8SBU7SJ69SRAT0L94BE",
            "lifecycleDateTime": "2014-10-28T21:20:07Z",
            "lifecycleStatus": {
                "type": "PROMOTED"
            },
            "number": "ECR-000001",
            "problem": "EveryRoad Model 300 is currently mounted directly to a car dashboard through a loop and hook (Velcro) system. Product management has received significant complaints that this mounting system does not work well on certain cars or the owners do not want to have adhesive on their dashboard.",
            "requestCode": "Performance",
            "requestedAction": "Find a method of mounting the EveryRoad GPS Model 300 which:\n1) Is flexible to fit on many different cars\n2) Does not require adhesive to be in direct contact with a car",
            "resolutionCode": "Approved [Immediate]",
            "submissionDateTime": "2011-07-20T22:16:33Z",
            "submitter": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "title": "Alternate Mounting Solution for EveryRoad GPS"
        }
    ]
}
```
