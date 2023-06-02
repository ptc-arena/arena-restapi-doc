# GET Event Items
/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items

Returns items of an outbound integrations matching the given search criteria.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all event items where results should begin. All event items before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400.  |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| reconciled  | string  | Reconciled can equal true, false, or any. Any will return GUIDs for reconciled and non-reconciled Items. If reconciled is omitted from the query string then the endpoint will assume a default value of false.  |
| reconciledDateTimeFrom  | Date-Formatted String  | The date in which the items in an event were reconciled. Often combined with reconciledDateTimeTo to search within a range. The search attribute assumes that reconciled is equal to true. If user provides both reconciledDateTimeFrom/reconciledDateTimeTo with the search attribute reconciled, then reconciled will not be assumed to be true but will be the value set by the user.  |
| reconciledDateTimeTo  | Date-Formatted String  | The date in which the items in an event were reconciled. Often combined with reconciledDateTimeFrom to search within a range. The search attribute assumes that reconciled is equal to true. If user provides both reconciledDateTimeFrom/reconciledDateTimeTo with the search attribute reconciled, then reconciled will not be assumed to be true but will be the value set by the user.  |

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
Get all non-reconciled Items associated with an event.

GET &lt;URL&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items?reconciled=false

```
{
    "count": 4,
    "results": [
        {
            "effectiveItemRevision": {
                "guid": "DVFYHUF6TWFN6OYHTLMW",
                "name": "Resistor, 1M Ohm, 1/16W, 5%, 0402, SMD",
                "number": "180-00008",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "O6Q9S5QH47IN6P8JA41O",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "8QATCPA1ORAI1JTCOHOD",
                "number": "180-00008",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "XFZI1EZQDGZ7Q8I1D56A",
                "name": "Resistor, 3K Ohm, 1/16W, 5%, 0603, SMD",
                "number": "180-00010",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "UCWFYBWNADOTCVEPGA7A",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "I0K3MZKBY1KSBT3MYRQA",
                "number": "180-00010",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "7P9SBO90NQ9H0ISBNFGV",
                "name": "Resistor, 2M Ohm, 1/16W, 5%, 0603, SMD",
                "number": "180-00011",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "XFZI1EZQDGRWFYHSJDAA",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "7P9SBO90NQ9H0ISBNGAO",
                "number": "180-00011",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "XFZI1EZQDGZ7Q535R6XM",
                "name": "Resistor, Surface Mount, 240ohm, 1/10W, 0603",
                "number": "180-00013",
                "revisionNumber": "01",
                "lifecyclePhase": {
                    "name": "Concept",
                    "stage": "DESIGN",
                    "guid": "4M6P8L6XKN58RATCU9I6"
                },
                "modifiedSpecs": true,
                "modifiedBom": true,
                "modifiedSourcing": true,
                "modifiedFiles": true
            },
            "guid": "3L5O7K5WJMX2L4NYPJGP",
            "reconciled": false
        }
    ]
}
```
Get all reconciled |Items associated with an event.

GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items?reconciled=true

```
{
    "count": 2,
    "results": [
        {
            "effectiveItemRevision": {
                "guid": "N5P8R4PG36PXGY8R3VWP",
                "name": "Resistor, 47 Ohm, 1/10W, 5%, 0603, SMD",
                "number": "180-00009",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "R9TCV8TK7ALQ9SBMD74N",
            "reconciled": true,
            "reconciledDateTime": "2020-03-16T01:40:30Z",
            "reconciledUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "supersededItemRevision": {
                "guid": "8QATCPA1ORAI1JTCOHK9",
                "number": "180-00009",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "I0K3MZKBY1KSBT3MYQQB",
                "name": "Resistor, 2.7K Ohm, 1/16W, 5%, 0402, SMD",
                "number": "180-00012",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "0I2L4H2TGJUZI1KVMGDQ",
            "reconciled": true,
            "reconciledDateTime": "2020-03-16T01:40:30Z",
            "reconciledUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "supersededItemRevision": {
                "guid": "2K4N6J4VIL4CVDN6IBY3",
                "number": "180-00012",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        }
    ]
}
```
Get all Items \(reconciled or non-reconciled\) associated with an event.

GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items?reconciled=any

```
{
    "count": 6,
    "results": [
        {
            "effectiveItemRevision": {
                "guid": "DVFYHUF6TWFN6OYHTLMW",
                "name": "Resistor, 1M Ohm, 1/16W, 5%, 0402, SMD",
                "number": "180-00008",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "O6Q9S5QH47IN6P8JA41O",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "8QATCPA1ORAI1JTCOHOD",
                "number": "180-00008",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "N5P8R4PG36PXGY8R3VWP",
                "name": "Resistor, 47 Ohm, 1/10W, 5%, 0603, SMD",
                "number": "180-00009",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "R9TCV8TK7ALQ9SBMD74N",
            "reconciled": true,
            "reconciledDateTime": "2020-03-16T01:40:30Z",
            "reconciledUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "supersededItemRevision": {
                "guid": "8QATCPA1ORAI1JTCOHK9",
                "number": "180-00009",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "XFZI1EZQDGZ7Q8I1D56A",
                "name": "Resistor, 3K Ohm, 1/16W, 5%, 0603, SMD",
                "number": "180-00010",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "UCWFYBWNADOTCVEPGA7A",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "I0K3MZKBY1KSBT3MYRQA",
                "number": "180-00010",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "7P9SBO90NQ9H0ISBNFGV",
                "name": "Resistor, 2M Ohm, 1/16W, 5%, 0603, SMD",
                "number": "180-00011",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "XFZI1EZQDGRWFYHSJDAA",
            "reconciled": false,
            "supersededItemRevision": {
                "guid": "7P9SBO90NQ9H0ISBNGAO",
                "number": "180-00011",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "I0K3MZKBY1KSBT3MYQQB",
                "name": "Resistor, 2.7K Ohm, 1/16W, 5%, 0402, SMD",
                "number": "180-00012",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "0I2L4H2TGJUZI1KVMGDQ",
            "reconciled": true,
            "reconciledDateTime": "2020-03-16T01:40:30Z",
            "reconciledUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "supersededItemRevision": {
                "guid": "2K4N6J4VIL4CVDN6IBY3",
                "number": "180-00012",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        {
            "effectiveItemRevision": {
                "guid": "XFZI1EZQDGZ7Q535R6XM",
                "name": "Resistor, Surface Mount, 240ohm, 1/10W, 0603",
                "number": "180-00013",
                "revisionNumber": "01",
                "lifecyclePhase": {
                    "name": "Concept",
                    "stage": "DESIGN",
                    "guid": "4M6P8L6XKN58RATCU9I6"
                },
                "modifiedSpecs": true,
                "modifiedBom": true,
                "modifiedSourcing": true,
                "modifiedFiles": true
            },
            "guid": "3L5O7K5WJMX2L4NYPJGP",
            "reconciled": false
        }
    ]
}
```
Get all Items \(reconciled or non-reconciled\) associated with an event within a specific date and time.

GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items?reconciledDateTimeFrom=2020-12-16T12:29:00Z&reconciledDateTimeTo=2020-12-18T23:59:59Z

```
{
    "count": 2,
    "results": [
        {
            "effectiveItemRevision": {
                "guid": "Q7B3R4PG36PXGY8R3VWP",
                "name": "Resistor, 48 Ohm, 1/10W, 5%, 0603, SMD",
                "number": "180-00019",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                },
                "modifiedSpecs": false,
                "modifiedBom": false,
                "modifiedSourcing": false,
                "modifiedFiles": false
            },
            "guid": "F5KJQ8TK7ALQ9SBMD74N",
            "reconciled": true,
            "reconciledDateTime": "2020-12-17T01:40:30Z",
            "reconciledUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "supersededItemRevision": {
                "guid": "9DHWTE1ORAI1JTCOHK9",
                "number": "180-00019",
                "revisionNumber": "A",
                "lifecyclePhase": {
                    "name": "In Production",
                    "stage": "PRODUCTION",
                    "guid": "DVFYHUF6TWEH0J2L4EYV"
                }
            }
        },
        ...
        }
    ]
}
```
