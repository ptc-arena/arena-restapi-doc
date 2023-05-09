# GET All Requests Associated with a Change


/changes/&lt;GUID&gt;/requests

Returns all  the requests associated with a specific change. Users must have a Read Change Summary and  Edit Change Requests rule for the Change. Additionally users must have a Read Request Summary rule for the request being added.

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
Get all requests associated with a change



GET /changes/&lt;GUID&gt;/requests

```
{
    "count": 3,
    "results": [
        {
            "guid": "J1L4N4N3ZCUI1K3BE6EB",
            "request": {
                "guid": "N5P8R8R73GZYH0J024AP",
                "number": "ECR-000001"
            }
        },
        {
            "guid": "K2M5O5O40DVJ2L4CF7F5",
            "request": {
                "guid": "Q8SBUBUA6J21K3M357DB",
                "number": "FFR-000001"
            }
        },
        {
            "guid": "L3N6P6P51EWK3M5DG8G4",
            "request": {
                "guid": "R9TCVCVB7K32L4N468E1",
                "number": "ECR-000002"
            }
        }
    ]
}   
```
Request with invalid GUID

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
