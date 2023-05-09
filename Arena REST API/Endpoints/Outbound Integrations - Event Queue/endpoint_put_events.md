# PUT Event


/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;

Updates the reconciliation status for all Items in an event with a given GUID.

The user must be an integration administrator for the integration in order to perform this activity.

When the event's itemsReconciled property is set to true, then all the event's items reconciled flags are set to true.

When the event's itemsReconciled property is set to false, then all the event's items reconciled flags are set to false.

If the itemsReconciled  is already set to the desired value \(i.e. set to true, but it is already true\), then the return response code will be 200, but the action will not be performed.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
```
{
    "itemsReconciled": true
}
```
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

## Sample Responses
Updates the reconcilation status for all Items in a specific event when itemsReconciled is true.



/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;

```
{
    "change": {
        "approvedOnDateTime": "2020-03-13T22:47:34Z",
        "category": {
            "categoryName": "Engineering Change Order",
            "categoryPath": "Change\\Change Order\\Engineering Change Order",
            "guid": "7P9SBO90NQ9J2L0778WO"
        },
        "effectiveDateTime": "2020-03-13T22:47:36Z",
        "effectivityType": "PERMANENT",
        "guid": "ZH1K3G1SFI14N5LLP1TU",
        "number": "ECO-000023",
        "title": "Critical Resistor Changes - Batch A"
    },
    "creationDateTime": "2020-03-13T22:47:36Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "eventType": "CHANGE",
    "guid": "4M6P8L6XKNY4N5LLP1T3",
    "itemsReconciled": true,
    "status": "RECONCILED"
}
```
If the request body has an itemsReconciled value of false, the response would resemble below.

```
{
    "change": {
        "approvedOnDateTime": "2020-03-13T22:47:34Z",
        "category": {
            "categoryName": "Engineering Change Order",
            "categoryPath": "Change\\Change Order\\Engineering Change Order",
            "guid": "7P9SBO90NQ9J2L0778WO"
        },
        "effectiveDateTime": "2020-03-13T22:47:36Z",
        "effectivityType": "PERMANENT",
        "guid": "ZH1K3G1SFI14N5LLP1TU",
        "number": "ECO-000023",
        "title": "Critical Resistor Changes - Batch A"
    },
    "creationDateTime": "2020-03-13T22:47:36Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "eventType": "CHANGE",
    "guid": "4M6P8L6XKNY4N5LLP1T3",
    "itemsReconciled": false,
    "status": "NEEDS_UPDATE"
}
```
Returns an error if:

* the format of the request is incorrect:

```
{
  "status": 400,
  "errors": [
    {
      "code": 400,
      "message": "The format of the request is not valid. Please check the syntax."
    }
  ]
}
```
* a GUID is invalid:

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"X9TCV8TK7AT1KZNA8V1Q\" is not valid."
    }
  ]
}
```
