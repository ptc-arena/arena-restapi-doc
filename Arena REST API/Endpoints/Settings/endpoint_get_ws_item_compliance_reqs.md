# GET Item Compliance Requirements
/settings/items/requirements

/settings/items/requirements/&lt;GUID&gt;

Returns   Compliance Requirements avaialble for items  in the workspace. Appending a GUID to the URL returns the requirement with that GUID.  

Note in the evidenceLocation attribute, if the allFileCategories attribute is set to *false* , the fileCategories attribute gives the categories in which evidence can be located.

## Request Header

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
Get all compliance requirements for items in the workspace

GET /settings/items/requirements

```
{  
   "count":5,
   "results":[  
      {  
         "defaultEvidenceType":"AML_AND_FILES",
         "evidenceLocation":{  
            "allFileCategories":false,
            "fileCategories":[  
               {  
                  "guid":"BTDWFNUGW4NXGZIZNMDM"
               },
               {  
                  "guid":"K2M5OW3P5DW6P8R8WVLS"
               }
            ]
         },
         "guid":"M4O7QY5R7FXXGZI07XHU",
         "invalidationRule":"RESET_ALL",
         "name":"RoHS (2002/95/EC)",
         "propagate":true,
         "rationaleHint":"- All off-the-shelf ...",
         "statementOfRequirement":"This Item ..."
      },
      {  
         "defaultEvidenceType":"NONE",
         "evidenceLocation":{  
            "allFileCategories":true
         },
         "guid":"EWGZIQXJZ7PP8RASY3JE",
         "invalidationRule":"RESET_ALL",
         "name":"api-requirement1",
         "propagate":false,
         "rationaleHint":"some rationale hint",
         "statementOfRequirement":"some statement of requirement"
      },
      ...
   ]
}
```
Get an item compliance requirements with a specific GUID

GET /settings/items/requirements/M4O7QY5R7FXXGZI07XHU

```
{  
   "defaultEvidenceType":"AML_AND_FILES",
   "evidenceLocation":{  
      "allFileCategories":false,
      "fileCategories":[  
         {  
            "guid":"BTDWFNUGW4NXGZIZNMDM"
         },
         {  
            "guid":"K2M5OW3P5DW6P8R8WVLS"
         }
      ]
   },
   "guid":"M4O7QY5R7FXXGZI07XHU",
   "invalidationRule":"RESET_ALL",
   "name":"RoHS (2002/95/EC)",
   "propagate":true,
   "rationaleHint":"- All off-the-shelf ...",
   "statementOfRequirement":"This Item ..."
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
