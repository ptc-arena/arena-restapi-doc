# GET Requests Categories


/settings/requests/categories



/settings/requests/categories/&lt;GUID&gt;

Returns  available for Requests. Appending a GUID to the URL returns the category with that GUID.

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all request categories



GET /settings/requests/categories

```
{
    "count": 14,
    "results": [
        {
            "activated": true,
            "assignable": true,
            "creationDateTime": "2008-03-07T19:02:39Z",
            "creator": {
                "email": "nlx.hmlrgfolhzmviz@mzeroofhn@www.xln",
                "fullName": "Eprn )Amviz( Nzeroofh",
                "guid": "VDXGZCXOBEVEXGZI1T4Q"
            },
            "description": null,
            "evaluatorGroupDefault": null,
            "guid": "FXH0JWH8VYHRAT8FFG40",
            "level": 3,
            "name": "Compliance Change Request",
            "numberingSequencePrefixDefault": {
                "guid": "7P9SBO90NQ62L4MOAVK1",
                "value": "CCR-"
            },
            "parentCategory": {
                "guid": "L3N6P2NE14NXGZELLMAW",
                "name": "Change Request"
            },
            "path": "Request\\Change Request\\Compliance Change Request",
            "structural": false,
            "systemDefined": false
        },
        {
            "activated": true,
            "assignable": true,
            "creationDateTime": "2008-03-07T19:05:17Z",
            "creator": {
                "email": "nlx.hmlrgfolhzmviz@mzeroofhn@www.xln",
                "fullName": "Eprn )Amviz( Nzeroofh",
                "guid": "VDXGZCXOBEVEXGZI1T4Q"
            },
            "description": null,
            "evaluatorGroupDefault": null,
            "guid": "GYI1KXI9WZISBU9GGH53",
            "level": 3,
            "name": "Document Change Request",
            "numberingSequencePrefixDefault": {
                "guid": "8QATCPA1OR73M5NPBWL9",
                "value": "DCR-"
            },
            "parentCategory": {
                "guid": "L3N6P2NE14NXGZELLMAW",
                "name": "Change Request"
            },
            "path": "Request\\Change Request\\Document Change Request",
            "structural": false,
            "systemDefined": false
        },
        {
            "activated": true,
            "assignable": true,
            "creationDateTime": "2008-03-07T19:15:34Z",
            "creator": {
                "email": "nlx.hmlrgfolhzmviz@mzeroofhn@www.xln",
                "fullName": "Eprn )Amviz( Nzeroofh",
                "guid": "VDXGZCXOBEVEXGZI1T4Q"
            },
            "description": "User this for Engineering changes",
            "evaluatorGroupDefault": null,
            "guid": "HZJ2LYJAX0JTCVAHHI66",
            "level": 3,
            "name": "Engineering Change Request",
            "numberingSequencePrefixDefault": {
                "guid": "ASCVERC3QT95O7PRDYND",
                "value": "ECR-"
            },
            "parentCategory": {
                "guid": "L3N6P2NE14NXGZELLMAW",
                "name": "Change Request"
            },
            "path": "Request\\Change Request\\Engineering Change Request",
            "structural": false,
            "systemDefined": false
        },
       ...
    ]
}
```
Get a Request category with a specific GUID



GET /settings/requests/categories/guid

```
{
    "activated": true,
    "assignable": true,
    "creationDateTime": "2008-03-07T19:15:34Z",
    "creator": {
        "email": "nlx.hmlrgfolhzmviz@mzeroofhn@www.xln",
        "fullName": "Eprn )Amviz( Nzeroofh",
        "guid": "VDXGZCXOBEVEXGZI1T4Q"
    },
    "description": "User this for Engineering changes",
    "evaluatorGroupDefault": null,
    "guid": "HZJ2LYJAX0JTCVAHHI66",
    "level": 3,
    "name": "Engineering Change Request",
    "numberingSequencePrefixDefault": {
        "guid": "ASCVERC3QT95O7PRDYND",
        "value": "ECR-"
    },
    "parentCategory": {
        "guid": "L3N6P2NE14NXGZELLMAW",
        "name": "Change Request"
    },
    "path": "Request\\Change Request\\Engineering Change Request",
    "structural": false,
    "systemDefined": false
}
```
