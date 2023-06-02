# GET Event Item Guids
/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/itemguids

Returns a list of Item revision GUIDs from an integration event.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Searchable Attributes

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| reconciled  | string  | Reconciled can equal true, false, or any. Any will return GUIDs for reconciled and non-reconciled Items. If reconciled is omitted from the query string then the endpoint will assume a default value of false.  |

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
Get the Item GUIDs of reconciled and non-reconciled Items from a specific event from a specific integration.

GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/itemguids?reconciled=any

```
{
    "count": 7,
    "results": [
        "DVFYHUF6TWFN6OYHTLOY",
        "N5P8R4PG36PXGY8R3VYR",
        "XFZI1EZQDGZ7Q8I1D58C",
        "8QATCPA1ORAI1JTCOGIQ",
        "I0K3MZKBY1KSBT3MYQSN",
        "SAUDW9UL8BU2L3DW8029",
        "2K4N6J4VIL4CVDN6IAC0"
    ]
}       
```
Get the Item GUIDs of non-reconciled Items from a specific event from a specific integration.

GET &lt;url&gt;/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/itemguids?reconciled=false

```
{
    "count": 4,
    "results": [
        "DVFYHUF6TWFN6OYHTLOY",
        "XFZI1EZQDGZ7Q8I1D58C",
        "I0K3MZKBY1KSBT3MYQSN",
        "2K4N6J4VIL4CVDN6IAC0"
    ]
}   
```
Get the Item GUIDs of reconciled Items from a specific event from a specific integration.

GET /outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/itemguids?reconciled=true

```
{
    "count": 3,
    "results": [
        "N5P8R4PG36PXGY8R3VYR",
        "8QATCPA1ORAI1JTCOGIQ",
        "SAUDW9UL8BU2L3DW8029"
    ]
}  
```
Request with an invalid GUID.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"4M6P8L6XKNY4N5LLP1T4\" is not valid."
      }
   ]
}
```
