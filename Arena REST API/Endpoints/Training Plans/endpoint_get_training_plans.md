# GET Training Plans (Search)
/trainingplans

Returns a collection of  Training Plan objects matching the given search criteria.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all changes where results should begin. All changes before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. By default the maximum number of items is 20. Can return up 400 changes.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| number<br> | string<br> | Training Plan number<br> |
| name<br> | string<br> | Training Plan name<br> |
| status<br> | string<br> | Status of the Training Plan. Possible values: "OPEN" or "CLOSED".<br> |
| manager.guid<br> | string<br> | The unique user id for the Training Manager. User unique ids can be obtained by the GET Users endpoint.<br> |
| manager.fullName<br> | string<br> | The first and last name of the Training Plan manager.<br> |
| user.guid<br> | string<br> | The unique user id for the users listed as trainees within the Training Plan.<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

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
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all Training Plans

GET /trainingplans

```
{
    "count": 2,
    "results": [
        {
            "creationDateTime": "2016-09-07T22:43:04Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "daysToComplete": 30,
            "description": "This Training Plan must be completed by all new Everyroad employees within 10 days of hire",
            "guid": "1J3M5I3UHK1M5O7Q9S0V",
            "manager": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Everyroad Employee Training",
            "number": "TRP-000002",
            "status": "OPEN"
        },
        {
            "creationDateTime": "2016-09-07T23:46:58Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "daysToComplete": 30,
            "description": "This training plan is to be completed by all Everyroad Document Control staff within 30 days of hire",
            "guid": "2K4N6J4VIL2N6P8RAT1F",
            "manager": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Document Control Training",
            "number": "TRP-000003",
            "status": "OPEN"
        }
    ]
}
```
Get the Training Plan with a number of TRP-000002.

GET &lt;url&gt;/trainingplans?number=TRP-000002

```
{
    "count": 1,
    "results": [
        {
            "creationDateTime": "2016-09-07T22:43:04Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "daysToComplete": 30,
            "description": "This Training Plan must be completed by all new Everyroad employees within 10 days of hire",
            "guid": "1J3M5I3UHK1M5O7Q9S0V",
            "manager": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "Everyroad Employee Training",
            "number": "TRP-000002",
            "status": "OPEN"
        }
    ]
}
```
Get all Training Plans with a status of CLOSED.

GET &lt;url&gt;/trainingplans?status=CLOSED

```
{
    "count": 1,
    "results": [
        {
            "creationDateTime": "2022-04-25T22:38:35Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "daysToComplete": 69,
            "description": "All employees must review Green 2022 Initiative. Please contact your manager or HR if you have any questions.",
            "guid": "FXH0JWH8VYF0J2L4NZB8",
            "manager": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
            "number": "TRP-000004",
            "status": "CLOSED"
        }
    ]
}
```
