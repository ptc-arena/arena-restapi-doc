# GET Events (Search)


/outboundintegrations/&lt;GUID&gt;/events

Returns unreconciled event objects matching the given search criteria. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Parameters

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| offset<br> | integer<br> | Specifies the position in the list of all events where results should begin. All events before the offset in the search results are ignored. The default value is 0.<br> |
| limit<br> | integer<br> | Specifies the number of results that should be returned. The default limit is 20. The maximum limit is 400.<br> |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| itemsReconciled<br> | string<br> | True returns all events that are reconciled. False returns all events that are not reconciled. Any returns events that are both reconciled and not reconciled.<br> |
| creationDateTimeFrom<br> | Date\-Formatted String<br> | The date in which the integration event was created. Typically coincides with the effective date of a Change or a revisioning event. Often combined with creationDateTimeTo to create a range.<br> |
| creationDateTimeTo<br> | Date\-Formatted String<br> | The date in which the integration event was created. Typically coincides with the effective date of a Change or a revisioning event. Often combined with creationDateTimeFrom to create a range.<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

Search in Zulu format is supported for custom attribute field type Date.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results.

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body


GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events

```
{
    "count": 4,
    "results": [
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:42:31Z",
                "effectiveDateTime": "2020-03-13T22:42:37Z",
                "effectivityType": "PERMANENT",
                "guid": "WEYH0DYPCFY1K2IIMYQ7",
                "number": "ECO-000022",
                "title": "Critical Changes"
            },
            "creationDateTime": "2020-03-13T22:42:37Z",
            "eventType": "CHANGE",
            "guid": "1J3M5I3UHKV1K2IIMYQ7",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:47:34Z",
                "effectiveDateTime": "2020-03-13T22:47:36Z",
                "effectivityType": "PERMANENT",
                "guid": "ZH1K3G1SFI14N5LLP1TU",
                "number": "ECO-000023",
                "title": "Critical Resistor Changes - Batch A"
            },
            "creationDateTime": "2020-03-13T22:47:36Z",
            "eventType": "CHANGE",
            "guid": "4M6P8L6XKNY4N5LLP1T3",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:51:34Z",
                "effectiveDateTime": "2020-03-13T22:51:35Z",
                "effectivityType": "PERMANENT",
                "guid": "1J3M5I3UHK36P7NNR3VD",
                "number": "ECO-000024",
                "title": "Critical Changes Resistors - Batch 2"
            },
            "creationDateTime": "2020-03-13T22:51:35Z",
            "eventType": "CHANGE",
            "guid": "6O8RAN8ZMP06P7NNR3VZ",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T23:51:14Z",
                "effectiveDateTime": "2020-03-13T23:51:15Z",
                "effectivityType": "PERMANENT",
                "guid": "4X7Q9B4WCS48G1USM7FL",
                "number": "ECO-000025",
                "title": "Critical Changes Resistors - Batch 3"
            },
            "creationDateTime": "2020-03-13T23:51:15Z",
            "eventType": "CHANGE",
            "guid": "612BDU3RQK72X2WOW3VQ",
            "itemsReconciled": true,
            "status": "NEEDS_UPDATE"
        }
    ]
}
```
Get events that are not reconciled with a limit of 400 results



GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events?itemsReconciled=false&limit=400

```
{
    "count": 3,
    "results": [
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:42:31Z",
                "effectiveDateTime": "2020-03-13T22:42:37Z",
                "effectivityType": "PERMANENT",
                "guid": "WEYH0DYPCFY1K2IIMYQ7",
                "number": "ECO-000022",
                "title": "Critical Changes"
            },
            "creationDateTime": "2020-03-13T22:42:37Z",
            "eventType": "CHANGE",
            "guid": "1J3M5I3UHKV1K2IIMYQ7",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:47:34Z",
                "effectiveDateTime": "2020-03-13T22:47:36Z",
                "effectivityType": "PERMANENT",
                "guid": "ZH1K3G1SFI14N5LLP1TU",
                "number": "ECO-000023",
                "title": "Critical Resistor Changes - Batch A"
            },
            "creationDateTime": "2020-03-13T22:47:36Z",
            "eventType": "CHANGE",
            "guid": "4M6P8L6XKNY4N5LLP1T3",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-03-13T22:51:34Z",
                "effectiveDateTime": "2020-03-13T22:51:35Z",
                "effectivityType": "PERMANENT",
                "guid": "1J3M5I3UHK36P7NNR3VD",
                "number": "ECO-000024",
                "title": "Critical Changes Resistors - Batch 2"
            },
            "creationDateTime": "2020-03-13T22:51:35Z",
            "eventType": "CHANGE",
            "guid": "6O8RAN8ZMP06P7NNR3VZ",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        }
    ]
}
```
Get events created within a specific time frame.



GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events?creationDateTimeFrom=2020\-10\-25T10:00:00Z&creationDateTimeTo=2020\-11\-11T12:20:00Z

```
{
    "count": 3,
    "results": [
        {
            "change": {
                "approvedOnDateTime": "2020-10-31T22:42:31Z",
                "effectiveDateTime": "2020-10-31T22:42:37Z",
                "effectivityType": "PERMANENT",
                "guid": "QWEDH0DYPCFY1K2IIMYQ7",
                "number": "ECO-000029",
                "title": "Critical Changes"
            },
            "creationDateTime": "2020-10-26T22:42:37Z",
            "eventType": "CHANGE",
            "guid": "BP9M5I3UHKV1K2IIMYQ7",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        {
            "change": {
                "approvedOnDateTime": "2020-10-31T22:47:34Z",
                "effectiveDateTime": "2020-10-31T22:47:36Z",
                "effectivityType": "PERMANENT",
                "guid": "QN4P3G1SFI14N5LLP1TU",
                "number": "ECO-000030",
                "title": "Critical Resistor Changes - Batch B"
            },
            "creationDateTime": "2020-10-28T22:47:36Z",
            "eventType": "CHANGE",
            "guid": "8J3C8L6XKNY4N5LLP1T3",
            "itemsReconciled": false,
            "status": "NEEDS_UPDATE"
        },
        ...   
    ]
}
```
Request with an invalid GUID.

GET /outboundintegrations/&lt;GUID&gt;/events

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"7D9W6F3TH0J3D9RATCFI\" is not valid."
      }
   ]
}
```
