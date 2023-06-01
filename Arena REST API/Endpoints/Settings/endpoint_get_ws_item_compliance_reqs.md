# GET Item Compliance Requirements
/settings/items/requirements

/settings/items/requirements/&lt;GUID&gt;

Returns   Compliance Requirements avaialble for items  in the workspace. Appending a GUID to the URL returns the requirement with that GUID.  

Note in the evidenceLocation attribute, if the allFileCategories attribute is set to false, the fileCategories attribute gives the categories in which evidence can be located.

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
