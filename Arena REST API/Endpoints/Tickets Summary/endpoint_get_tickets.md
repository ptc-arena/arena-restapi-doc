# GET Tickets
/tickets

Returns a collection of Ticket   objects matching the given search criteria.

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
| \[additional attribute guid value\]<br> | string<br> | This special search permits searching for strings in additional attribute values. For example GET /tickets?VDXGZ7E0GO5N6P8PR55G=\*100pF where VDXGZ7E0GO5N6P8PR55G is the GUID of a custom attribute and we are searching for all items whose value for this attribute include the string "100pF". The ability to search for more than one value is available for the following attribute field types: DROP_DOWN & FIXED_DROPDOWN \(where multi-select is true\). See note below this table for additional details.<br>Additional attributes, also known as custom attributes, support the date field type. Users can perform searches by additional attributes with a date field type by using the format yyyy-mm-dd. In the following example, the user is using the following to search for a date field type custom attribute with a value of April 1, 2019:<br>GET /tickets?4M6PUJNPNM3L4N25ZZ5F=2019-04-01<br> |
| template.guid<br> | string<br> | template unique ID<br> |
| status<br> | string<br> | status of the ticket. Values can be , , or .<br>NOT_STARTED<br>IN_PROGRESS<br>COMPLETE<br> |
| number<br> | string<br> | number of the ticket<br> |
| title<br> | string<br> | title of the ticket<br> |

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
Get all tickets

GET /tickets

```
{
    "count": 6,
    "results": [
        {
            "additionalAttributes": [
                {
                    "apiName": "ASCVERC3QTASBUDWFYJ0",
                    "fieldType": "MULTI_LINE_TEXT",
                    "guid": "ASCVERC3QTASBUDWFYJ0",
                    "name": "Reason",
                    "value": "Exceeding max power draw can result in overheating and melting."
                },
                {
                    "apiName": "9RBUDQB2PS9RATCVEXID",
                    "fieldType": "MULTI_LINE_TEXT",
                    "guid": "9RBUDQB2PS9RATCVEXID",
                    "name": "Risk",
                    "value": "Risk of fire"
                },
                {
                    "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "6O8RAN8ZMP6O7Q9SBUGT",
                    "name": "Components",
                    "value": null
                },
                {
                    "apiName": "5N7Q9M7YLO5N6P8RATF6",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "5N7Q9M7YLO5N6P8RATF6",
                    "name": "Labels",
                    "value": null
                }
            ],
            "assignee": null,
            "creationDateTime": "2017-03-17T22:27:02Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "",
            "fixVersion": null,
            "guid": "ASCVERC3QTAP8RATCUF0",
            "modifyDateTime": "2017-03-17T22:27:39Z",
            "title": "500 PCBA: Max Power draw 10V",
            "number": "REQ-000005",
            "priority": "Critical",
            "status": {
                "guid": "TBVEXAVM9CTP8RATCVFU",
                "value": "Not Started"
            },
            "template": {
                "guid": "9RBUDQB2PS94N6P8RA7Y",
                "name": "Requirements"
            }
        },
        {
            "additionalAttributes": [
                {
                    "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "6O8RAN8ZMP6O7Q9SBUGT",
                    "name": "Components",
                    "value": null
                },
                {
                    "apiName": "5N7Q9M7YLO5N6P8RATF6",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "5N7Q9M7YLO5N6P8RATF6",
                    "name": "Labels",
                    "value": null
                }
            ],
            "assignee": {
                "email": "jparker@everyroadgps.com",
                "fullName": "John Parker",
                "guid": "XFZI1EZQDGXGZI1KTJQ2"
            },
            "creationDateTime": "2017-03-17T22:48:02Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "<p>The power draw is too high on the 500 board, violating the requirement.</p>",
            "fixVersion": null,
            "foundOn": null,
            "guid": "GYI1KXI9WZGVEXGZI0K9",
            "modifyDateTime": "2017-03-21T23:32:18Z",
            "title": "500 board drawing 10.5V",
            "number": "DEF-000002",
            "priority": "Critical",
            "status": {
                "guid": "R9TCV8TK7ARN6P8RATDZ",
                "value": "In Progress"
            },
            "template": {
                "guid": "8QATCPA1OR83M5O7Q967",
                "name": "Defects"
            }
        },
        {
            "additionalAttributes": [
                {
                    "apiName": "5N7Q9M7YLO5N6P8RATF6",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "5N7Q9M7YLO5N6P8RATF6",
                    "name": "Labels",
                    "value": null
                },
                {
                    "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "6O8RAN8ZMP6O7Q9SBUGT",
                    "name": "Components",
                    "value": "Model 600"
                }
            ],
            "assignee": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "creationDateTime": "2021-09-06T23:47:26Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "<p>Screws on Chassis Prone to rust.</p><p>We switched screws in release 2.50 to reduce cost, but QA has observed that the screws are more prone to rust.</p>",
            "fixVersion": null,
            "foundOn": "3.0",
            "guid": "YG0J2F0REHYDWFYH0YI1",
            "modifyDateTime": "2021-09-06T23:47:27Z",
            "title": "Screws on Chassis Prone to Rust",
            "number": "DEF-000003",
            "priority": "High",
            "status": {
                "guid": "Q8SBU7SJ69QM5O7Q9SCG",
                "value": "Not Started"
            },
            "template": {
                "guid": "8QATCPA1OR83M5O7Q967",
                "name": "Defects"
            }
        },
        ...
    ]
}
```
Get  tickets with a status of IN_PROGRESS and a template of  Defects

GET &lt;url&gt;/tickets?status=IN_PROGRESS&template.guid=8QATCPA1OR83M5O7Q967

```
{
    "count": 1,
    "results": [
        {
            "additionalAttributes": [
                {
                    "apiName": "6O8RAN8ZMP6O7Q9SBUGT",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "6O8RAN8ZMP6O7Q9SBUGT",
                    "name": "Components",
                    "value": null
                },
                {
                    "apiName": "5N7Q9M7YLO5N6P8RATF6",
                    "fieldType": "SINGLE_LINE_TEXT",
                    "guid": "5N7Q9M7YLO5N6P8RATF6",
                    "name": "Labels",
                    "value": null
                }
            ],
            "assignee": {
                "email": "jparker@everyroadgps.com",
                "fullName": "John Parker",
                "guid": "XFZI1EZQDGXGZI1KTJQ2"
            },
            "creationDateTime": "2017-03-17T22:48:02Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "description": "<p>The power draw is too high on the 500 board, violating the requirement.</p>",
            "fixVersion": null,
            "foundOn": null,
            "guid": "GYI1KXI9WZGVEXGZI0K9",
            "modifyDateTime": "2017-03-21T23:32:18Z",
            "title": "500 board drawing 10.5V",
            "number": "DEF-000002",
            "priority": "Critical",
            "status": {
                "guid": "R9TCV8TK7ARN6P8RATDZ",
                "value": "In Progress"
            },
            "template": {
                "guid": "8QATCPA1OR83M5O7Q967",
                "name": "Defects"
            }
        }
    ]
}
```
