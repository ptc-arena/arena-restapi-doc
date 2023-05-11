# GET Event Item Guids


/outboundintegrations/&lt;GUID&gt;/events/&lt;GUID&gt;/itemguids

Returns a list of Item revision GUIDs from an integration event.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| reconciled<br> | string<br> | Reconciled can equal true, false, or any. Any will return GUIDs for reconciled and non\-reconciled Items. If reconciled is omitted from the query string then the endpoint will assume a default value of false.<br> |

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
Get the Item GUIDs of reconciled and non\-reconciled Items from a specific event from a specific integration.

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
Get the Item GUIDs of non\-reconciled Items from a specific event from a specific integration.



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
