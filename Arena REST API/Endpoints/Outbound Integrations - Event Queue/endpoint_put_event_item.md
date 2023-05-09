# PUT Event Item


/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

The final GUID in the above URL refers to the Event Item GUID and not the revision Item GUID.

Updates the reconciliation status for a specific event Item with a GUID  in an event with a given GUID.

The user must be an integration administrator for the integration in order to perform this activity.

The event's itemsReconciled property depends on the event item's reconciled property. Changing the event item reconciled property may change the event's itemsReconciled property.

If the item's Reconciled property  is already set to the desired value \(i.e. set to true, but it is already true\), then the return response code will be 200, but the action will not be performed.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body
```
{
    "reconciled": true
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
Below is the response when the Request Body has a reonciled value of true.



/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

```
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
    "reconciledDateTime": "2020-03-16T04:33:21Z",
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
}
```
If the request body has an itemsReconciled value of false, the response would resemble below.



/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/items/&lt;GUID&gt;

```
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
    "reconciled": false,
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
