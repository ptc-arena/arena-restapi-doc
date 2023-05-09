# GET Supplier Item Compliance Requirements


/settings/supplieritems/requirements



/settings/supplieritems/requirements/&lt;GUID&gt;

Returns all supplier item  objects  in the workspace. Appending a GUID to the URL returns the requirement with that GUID.  

Note in the evidenceLocation attribute, if the allFileCategories attribute is set to , the fileCategories attribute gives the categories in which evidence can be located.

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

## Sample Response Body
Get all compliance requirements for supplier items in the workspace



GET /settings/supplieritems/requirements

```
{  
   "count":3,
   "results":[  
      {  
         "defaultEvidenceType":"DIRECT_FILES",
         "evidenceLocation":{  
            "allFileCategories":false,
            "fileCategories":[  
               {  
                  "guid":"5N7QVLMMV2LVEX9H5Y6T"
               },
               {  
                  "guid":"I0K38YZZ8FY8RAMUIBIK"
               }
            ]
         },
         "guid":"8QATYOPPY5NM5O61JCQW",
         "name":"2002/95/EC RoHS (Sample)",
         "rationaleHint":"- This Supplier Item has been verified to meet the RoHS requirement.\n- This is a make-to-specification Supplier Item. RoHS requirements called out by design & mfr requirements. See Item specs files. Verified by sample at IQA during production, documented in IQA test reports.",
         "statementOfRequirement":"This Item, and all its approved sourced Supplier Items, meet the 2002/95/EC RoHS requirements of Pb<0.1%, Hg<0.1%, Cr6<0.1%, PBB<0.1%, PBDE<0.1%, Cd<0.01% by weight in each homogeneous material in each Supplier Item."
      },
      ...
   ]
}
```
Get a single supplier item compliance requirement



GET /settings/supplieritems/requirements/8QATYOPPY5NM5O61JCQW

```
{  
   "defaultEvidenceType":"DIRECT_FILES",
   "evidenceLocation":{  
      "allFileCategories":false,
      "fileCategories":[  
         {  
            "guid":"5N7QVLMMV2LVEX9H5Y6T"
         },
         {  
            "guid":"I0K38YZZ8FY8RAMUIBIK"
         }
      ]
   },
   "guid":"8QATYOPPY5NM5O61JCQW",
   "name":"2002/95/EC RoHS (Sample)",
   "rationaleHint":"- This Supplier Item has been verified to meet the RoHS requirement.\n- This is a make-to-specification Supplier Item. RoHS requirements called out by design & mfr requirements. See Item specs files. Verified by sample at IQA during production, documented in IQA test reports.",
   "statementOfRequirement":"This Item, and all its approved sourced Supplier Items, meet the 2002/95/EC RoHS requirements of Pb<0.1%, Hg<0.1%, Cr6<0.1%, PBB<0.1%, PBDE<0.1%, Cd<0.01% by weight in each homogeneous material in each Supplier Item."
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
