# PUT Supplier Item Compliance Update


PUT /supplierItems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

Updates a  object with a given GUID  for a supplier item with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set mark or rationale to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

## Sample Request Body
PUT /supplierItems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{  
   "evidenceType":"DIRECT_FILES",
   "mark":"blue checkmark on packaging",
   "rationale":"evidence provided by files attached to supplier item",
   "status":"COMPLIANT"
}
```
PUT /supplierItems/&lt;GUID&gt;/compliance/&lt;GUID&gt;?setnull=true

```
{  
   "mark":null
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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
Update a compliance requirement for a supplier item



PUT /supplieritems/&lt;GUID&gt;/compliance/&lt;GUID&gt;

```
{  
   "evidenceType":"DIRECT_FILES",
   "guid":"WEXGZI0ZI1K30FUO",
   "lastModifiedBy":{  
      "fullName":"Heidi Walker"
   },
   "lastModifiedDateTime":"07/31/2015 05:50:26 PM",
   "mark":null,
   "rationale":"evidence provided by files attached to supplier item",
   "requirement":{  
      "guid":"GYI1KSZL19RQ9SBTZ4KV",
      "name":"2011/65/EU RoHS"
   },
   "status":"COMPLIANT"
}
```
Set a Supplier Item Compliance attribute to null.

PUT /supplierItems/&lt;GUID&gt;/compliance/&lt;GUID&gt;?setnull=true

```
{  
   "evidenceType":"DIRECT_FILES",
   "guid":"WEXGZI0ZI1K30FUO",
   "lastModifiedBy":{  
      "fullName":"Heidi Walker"
   },
   "lastModifiedDateTime":"07/31/2015 05:50:26 PM",
   "mark":"blue checkmark on packaging",
   "rationale":"evidence provided by files attached to supplier item",
   "requirement":{  
      "guid":"GYI1KSZL19RQ9SBTZ4KV",
      "name":"2011/65/EU RoHS"
   },
   "status":"COMPLIANT"
}
```
Returns an error if the evidence type or status is not valid.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
