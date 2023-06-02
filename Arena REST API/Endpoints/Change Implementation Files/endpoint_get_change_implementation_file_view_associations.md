# GET Change Implementation Files View Associations
/changes/&lt;GUID&gt;/implementationfiles

Returns a list of file objects associated with the Implementation view of a Change with a specific GUID.


| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

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
Change Implementation View  Associations

GET &lt;url&gt;/changes/&lt;GUID&gt;/implementationfiles

```
{
    "count": 4,
    "results": [
        {
            "file": {
                "author": {
                    "fullName": "Bret D Lobree"
                },
                "category": {
                    "guid": "TBVEXAVM9CV5O7MTTUH9"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-02T19:30:28Z",
                "description": null,
                "edition": "1",
                "format": "pdf",
                "guid": "9RBUDQB2PSBRATWN9FV3",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T19:30:28Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "NDT456P.pdf",
                "number": "FILE-000815",
                "private": false,
                "size": 101958,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "NDT456P"
            },
            "guid": "FXH0JWH8VYC0J2EYESP7"
        },
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
        },
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
                "description": "NEC Datasheet for NL4864HL11-01B 3.5 inch LCD touch screen",
                "edition": "1",
                "format": null,
                "guid": "6O8RAN8ZMP8O7QTK6CSN",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T19:30:28Z",
                "latest": true,
                "location": "http://www.nec-lcd.com/en/products/nl4864hl11-01b.html",
                "locked": true,
                "mimeType": null,
                "name": null,
                "number": "FILE-000935",
                "private": false,
                "size": 0,
                "storageMethod": 3,
                "storageMethodName": "WEB",
                "title": "NEC Datasheet for NL4864HL11-01B"
            },
            "guid": "DVFYHUF6TWAYH0CWCQNV"
        },
        {
            "file": {
                "author": {
                    "fullName": "Nathan Martin"
                },
                "category": {
                    "guid": "7P9SBO90NQ9J2L0778VN"
                },
                "checkedOut": false,
                "corrected": false,
                "creationDateTime": "2011-06-02T19:30:28Z",
                "description": "See Item_Number schema for compliance status",
                "edition": "1",
                "format": "pdf",
                "guid": "Q8SBU7SJ69S8RAD4QWBR",
                "hasMarkup": false,
                "lastModifiedDateTime": "2011-06-02T19:30:28Z",
                "latest": true,
                "location": null,
                "locked": true,
                "mimeType": "application/pdf",
                "name": "NRC06J474TR_NICCS01262-1.pdf",
                "number": "FILE-000873",
                "private": false,
                "size": 136411,
                "storageMethod": 0,
                "storageMethodName": "FILE",
                "title": "NRC06J474TR_NICCS01262-1"
            },
            "guid": "CUEXGTE5SV9XGZBVBPM7"
        }
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
