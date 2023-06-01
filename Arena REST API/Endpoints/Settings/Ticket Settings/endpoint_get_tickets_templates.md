# GET Tickets Templates
/settings/tickets/templates

/settings/tickets/templates/&lt;GUID&gt;

Returns templates available for Tickets. Appending a GUID to the URL returns the category with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Searchable Attributes (for GET /settings/tickets/templates only)

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | Ticket template name<br> |
| active<br> | true or false<br> | true indicates active templates.<br>false indicates inactive templates.<br> |

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
Get all ticket templates

GET /settings/tickets/templates

```
{
    "count": 3,
    "results": [
        {
            "active": false,
            "allowUserDefinedNumber": false,
            "creationDateTime": "2017-03-21T23:40:43Z",
            "creator": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "defaultAssignee": {
                "email": "tshaftoe@everyroadgps.com",
                "fullName": "Tony Shaftoe",
                "guid": "0I2L4H2TGJ0J2L4NWMTA"
            },
            "defaultNumberSequence": {
                "guid": "O6Q9S5QH47QZI1K3M5F4",
                "name": "Defects",
                "prefixes": [
                    {
                        "guid": "M4O7Q3OF25LH0J2L4NWL",
                        "value": "DEF-"
                    }
                ]
            },
            "defaultTemplate": false,
            "description": "Use for all bugs",
            "guid": "2K4N6J4VIL2XGZI1K138",
            "name": "Bugs",
            "numberSequences": [
                {
                    "guid": "O6Q9S5QH47QZI1K3M5F4",
                    "name": "Defects",
                    "prefixes": [
                        {
                            "guid": "M4O7Q3OF25LH0J2L4NWL",
                            "value": "DEF-"
                        }
                    ]
                }
            ]
        },
        {
            "active": true,
            "allowUserDefinedNumber": true,
            "creationDateTime": "2016-11-13T17:12:52Z",
            "creator": {
                "email": null,
                "fullName": "Arena Solutions",
                "guid": "CUEXGTE5SVCVEXGZI1K2"
            },
            "defaultAssignee": null,
            "defaultNumberSequence": {
                "guid": "O6Q9S5QH47QZI1K3M5F4",
                "name": "Defects",
                "prefixes": [
                    {
                        "guid": "M4O7Q3OF25LH0J2L4NWL",
                        "value": "DEF-"
                    }
                ]
            },
            "defaultTemplate": false,
            "description": "Seeded Template for Defects",
            "guid": "8QATCPA1OR83M5O7Q967",
            "name": "Defects",
            "numberSequences": [
                {
                    "guid": "O6Q9S5QH47QZI1K3M5F4",
                    "name": "Defects",
                    "prefixes": [
                        {
                            "guid": "M4O7Q3OF25LH0J2L4NWL",
                            "value": "DEF-"
                        }
                    ]
                }
            ]
        },
        {
            "active": true,
            "allowUserDefinedNumber": true,
            "creationDateTime": "2016-11-13T17:12:52Z",
            "creator": {
                "email": null,
                "fullName": "Arena Solutions",
                "guid": "CUEXGTE5SVCVEXGZI1K2"
            },
            "defaultAssignee": null,
            "defaultNumberSequence": {
                "guid": "N5P8R4PG36PYH0J2L4EY",
                "name": "Requirements",
                "prefixes": [
                    {
                        "guid": "L3N6P2NE14KGZI1K3MVY",
                        "value": "REQ-"
                    }
                ]
            },
            "defaultTemplate": false,
            "description": "Seeded Template for Requirements",
            "guid": "9RBUDQB2PS94N6P8RA7Y",
            "name": "Requirements",
            "numberSequences": [
                {
                    "guid": "N5P8R4PG36PYH0J2L4EY",
                    "name": "Requirements",
                    "prefixes": [
                        {
                            "guid": "L3N6P2NE14KGZI1K3MVY",
                            "value": "REQ-"
                        }
                    ]
                }
            ]
        }
    ]
}
```
Get all active templates.

GET /settings/tickets/templates?active=true

```
{
    "count": 2,
    "results": [
        {
            "active": true,
            "allowUserDefinedNumber": true,
            "creationDateTime": "2016-11-13T17:12:52Z",
            "creator": {
                "email": null,
                "fullName": "Arena Solutions",
                "guid": "P7RAF47O4VCVEXGZI1K1"
            },
            "defaultAssignee": null,
            "defaultNumberSequence": {
                "guid": "6O8RWLO5LCV4N6P8R8T8",
                "name": "Defects",
                "prefixes": [
                    {
                        "guid": "P7RAF47O4VB7Q9SBUAT8",
                        "value": "DEF-"
                    }
                ]
            },
            "defaultTemplate": false,
            "description": "Seeded Template for Defects",
            "guid": "6O8RWLO5LCTO7Q9SB9W4",
            "name": "Defects",
            "numberSequences": [
                {
                    "guid": "6O8RWLO5LCV4N6P8R8T8",
                    "name": "Defects",
                    "prefixes": [
                        {
                            "guid": "P7RAF47O4VB7Q9SBUAT8",
                            "value": "DEF-"
                        }
                    ]
                }
            ]
        },
        {
            "active": true,
            "allowUserDefinedNumber": true,
            "creationDateTime": "2016-11-13T17:12:52Z",
            "creator": {
                "email": null,
                "fullName": "Arena Solutions",
                "guid": "P7RAF47O4VCVEXGZI1K1"
            },
            "defaultAssignee": null,
            "defaultNumberSequence": {
                "guid": "5N7QVKN4KBU3M5O7Q7SD",
                "name": "Requirements",
                "prefixes": [
                    {
                        "guid": "Q8SBG58P5WC8RATCVBU1",
                        "value": "REQ-"
                    }
                ]
            },
            "defaultTemplate": false,
            "description": "Seeded Template for Requirements",
            "guid": "7P9SXMP6MDUP8RATCAX0",
            "name": "Requirements",
            "numberSequences": [
                {
                    "guid": "5N7QVKN4KBU3M5O7Q7SD",
                    "name": "Requirements",
                    "prefixes": [
                        {
                            "guid": "Q8SBG58P5WC8RATCVBU1",
                            "value": "REQ-"
                        }
                    ]
                }
            ]
        }
    ]
}
```
Get a ticket template with a specific GUID

GET /settings/tickets/templates/guid

```
{
    "activated": true,
    "assignable": true,
    "creationDateTime": "2008-03-07T19:15:34Z",
    "creator": {
        "email": "nlx.hmlrgfolhzmviz@mzeroofhn@www.xln",
        "fullName": "Eprn )Amviz( Nzeroofh",
        "guid": "VDXGZCXOBEVEXGZI1T4Q"
    },
    "description": "User this for Engineering changes",
    "evaluatorGroupDefault": null,
    "guid": "HZJ2LYJAX0JTCVAHHI66",
    "level": 3,
    "name": "Engineering Change Request",
    "numberingSequencePrefixDefault": {
        "guid": "ASCVERC3QT95O7PRDYND",
        "value": "ECR-"
    },
    "parentCategory": {
        "guid": "L3N6P2NE14NXGZELLMAW",
        "name": "Change Request"
    },
    "path": "Request\\Change Request\\Engineering Change Request",
    "structural": false,
    "systemDefined": false
}
```
