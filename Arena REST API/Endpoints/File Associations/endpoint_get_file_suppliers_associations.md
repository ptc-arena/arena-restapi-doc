# GET File Supplier Associations


/files/&lt;GUID&gt;/suppliers

Returns a list of Supplier association GUIDs \(and limited information about the associated Supplier\) for a File with a given GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

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
