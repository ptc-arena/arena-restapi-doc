# PUT Supplier Phone Number Edit


/suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;

Updates the existing phone numbers of a  with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set comment,extension, label, number to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

## Sample Request Body
PUT /suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;

```
{
   "comment": "Priya Chang",
   "extension": "x3910",  
   "label": "Main Researcher",
   "number": "512-746-3781"     
}
```
PUT /suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;?setnull=true

```
{ 
   "label":null    
}
```
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
Update a specific phone number of a supplier.



/suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;

```
{
   "comment": "Priya Chang",
   "extension": "x3910",
   "guid":"I0K3MU330HYGZI1K9K72",
   "label": "Main Researcher",
   "number": "512-746-3781"     
}   
```
Set a Supplier Phone attribute to null.

PUT /suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;?setnull=true

```
{
   "comment": "Priya Chang",
   "extension": "x3910",
   "guid":"I0K3MU330HYGZI1K9K72",
   "label": null,
   "number": "512-746-3781"     
}  
```
Request with bad GUID

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
