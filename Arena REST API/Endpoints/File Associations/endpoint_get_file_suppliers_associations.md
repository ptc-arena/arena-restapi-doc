# GET File Supplier Associations


/files/&lt;GUID&gt;/suppliers

Returns a list of Supplier association GUIDs \(and limited information about the associated Supplier\) for a File with a given GUID. 

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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

## Sample Response Body
Get a File's Supplier   associations

 

GET &lt;url&gt;/files/&lt;GUID&gt;/suppliers

```
{  
   "count":6,
   "results":[  
      {  
         "guid":"5N7QVLMMV2JRATA2GJ6E",
         "supplier":{  
            "guid":"UCWFKABBKRAGZINDEEM1",
            "name":"Avnet"
         }
      },
      {  
         "guid":"9V3Q9M7YLOZ3M5GLXZ0K",
         "supplier":{  
            "guid":"YG0J2AJJGXGM5O7FOOG1",
            "name":"Adaptive Circuit Boards"
         }
      },
      {  
         "guid":":DB1K3G1SFITXGZBRWP1K",
         "supplier":{  
            "guid":"UCWFY6FFCTCI1K3B82OC",
            "name":"The Board Room"
         }
      },
      ...
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
