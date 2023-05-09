# PUT Supplier Phone Number Edit


/suppliers/&lt;GUID&gt;/phonenumbers/&lt;GUID&gt;

Updates the existing phone numbers of a  with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set comment,extension, label, number to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

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
