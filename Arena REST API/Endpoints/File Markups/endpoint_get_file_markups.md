# GET File Markups


/files/&lt;GUID&gt;/markups

Returns a collection of Markup Files associated with a specific File.

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

## Sample Responses
Get  File Markups of a File  with a given GUID



GET &lt;url&gt;/files/&lt;GUID&gt;/markups

```
{
    "count": 5,
    "results": [
        {
            "guid": "XFZI1EZQDGUJ2LN69BYZ",
            "markup": {
                "author": {
                    "fullName": "Tony Shaftoe"
                },
                "category": {
                    "guid": "0I2L4H2TGJ2CVET001OY"
                },
                "creationDateTime": "2011-07-25T22:38:18Z",
                "format": "doc",
                "guid": "1J3M5I3UHK3J2LN69BYY",
                "lastModifiedDateTime": "2011-07-25T22:38:18Z",
                "locked": true,
                "mimeType": "application/msword",
                "name": "mount-instructions-07-25-2011.doc",
                "size": 27136,
                "storageMethodName": "FILE",
                "title": "mount-instructions-07-25-2011"
            },
            "markupOf": {
                "edition": "1",
                "guid": "UCWFYBWNADWCVEGZ24RC",
                "number": "FILE-000944"
            },
            "request": {
                "guid": "Q8SBU7SJ69SRAT0L94BE",
                "number": "ECR-000001"
            },
            "reserved": false
        },
        {
            "guid": "2K4N1Y24FWFN6LDUC67B",
            "markup": {
                "author": {
                    "fullName": "Heidi Walker"
                },
                "category": {
                    "guid": "3L507K5WJM5FYHW334R7"
                },
                "creationDateTime": "2020-11-25T12:38:18Z",
                "format": "PDF",
                "guid": "WEYH0DYPCFYEXG6DWC0X",
                "lastModifiedDateTime": "2020-12-12T11:21:18Z",
                "locked": true,
                "mimeType": "application/PDF",
                "name": "mount-instructions-VARIANT-Winter-2020.doc",
                "size": 45136,
                "storageMethodName": "FILE",
                "title": "mount-instructions-10-25-2020"
            },
            "markupOf": {
                "edition": "1",
                "guid": "UCWFYBWNADWCVEGZ24RC",
                "number": "FILE-000944"
            },
            "change": {
                "guid": "TBVESPTV6N6ILKFS6B7N",
                "number": "ECo-000042"
            },
            "reserved": false
        },
        ...
    ]
}
```
Returns an error if a parameter is not a valid search attribute.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3019,
         "message":"The attribute \"edition\" is not searchable."
      }
   ]
}
```
