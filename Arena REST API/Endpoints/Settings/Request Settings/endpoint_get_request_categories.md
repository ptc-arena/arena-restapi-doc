# GET Requests Categories


/settings/requests/categories



/settings/requests/categories/&lt;GUID&gt;

Returns  available for Requests. Appending a GUID to the URL returns the category with that GUID.

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
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
