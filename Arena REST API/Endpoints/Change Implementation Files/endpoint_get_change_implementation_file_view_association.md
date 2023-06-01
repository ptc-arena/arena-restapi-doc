# GET Change Implementation Files View Association
/changes/&lt;GUID&gt;/implementationfiles/&lt;GUID&gt;

Returns a File object located within the Implementation Files view of a Change with a specific GUID. 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Change Implementation Views  Association

GET &lt;url&gt;/files/&lt;GUID&gt;/implementationfiles/&lt;GUID&gt;

```
{
    "file": {
        "author": {
            "fullName": "Helen Shaughnessy"
        },
        "category": {
            "guid": "TBVEXAVM9CV5O7MTTUH9"
        },
        "checkedOut": false,
        "corrected": false,
        "creationDateTime": "2011-06-02T19:30:28Z",
        "description": "NEC Product Spec for touch screen model - nl4864hl11-01b",
        "edition": "1",
        "format": "pdf",
        "guid": "HZJ2LYJAX0JZI14VHN4J",
        "hasMarkup": false,
        "lastModifiedDateTime": "2011-06-02T19:30:28Z",
        "latest": true,
        "location": null,
        "locked": true,
        "mimeType": "application/pdf",
        "name": "NEC - TouchLCD-NL4864HL11-01B.pdf",
        "number": "FILE-000911",
        "private": false,
        "size": 251396,
        "storageMethod": 0,
        "storageMethodName": "FILE",
        "title": "NEC - TouchLCD-NL4864HL11-01B"
    },
    "guid": "EWGZIVG7UXBZI1DXDRO2"
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
