# GET Quality Process Templates


/settings/qualityprocesses/templates



/settings/qualityprocesses/templates/&lt;GUID&gt;

This returns   available for Quality Processes in the workspace. Appending a GUID to the URL returns the template with that GUID.  

All Quality Processes must be created based on templates. These templates are administrator\-defined and can include Steps and Sign\-Off Steps. In the response, Steps are indicated as Type=REGULAR and Sign\-Off Steps are indicated as Type=SIGNOFF.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Searchable Attributes (for GET /settings/qualityprocesses/templates only)

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| name<br> | string<br> | Quality Process template name<br> |
| active<br> | true or false<br> | true indicates template is active<br>false indicates template is inactive<br> |

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
Get all Quality Process Templates defined for the workspace



GET /settings/qualityprocesses/templates

```
{  
   "count":3,
   "results":[  
      {  
         "active":true,
         "creationDateTime":"2015-12-14T19:49:08Z",
         "creator":{  
            "fullName":"Cole Agustin"
         },
         "defaultNumberFormat":{  
            "guid":"YG0J2A8OX0JSBUDWFUYM"
         },
         "defaultOwner":{  
            "fullName":"Roy Stafford",
            "guid":"GY116WXX6DUDWFYHPRY3"
         },
         "description":"Eight Discipline (8D)",
         "guid":"HZJ2LTR7GJ2YH0J2LJAP",
         "name":"Eight Discipline (8D) Template",
         "numberFormats":[  
            {  
               "guid":"YG0J2A8OX0JSBUDWFUYM",
               "lastUsed":null,
               "prefixes":[  
                  {  
                     "guid":"SAUDW42IRUCWFYH0JYZ4",
                     "value":"8D-"
                  }
               ]
            }
         ],
         "shortName":"8D",
         "steps":[  
            {  
               "attributes":[  
                  {  
                     "guid":"I0K3MUS8HK3ZI1K3MZ01",
                     "name":"Team Members"
                  }
               ],
               "guid":"K2M5OWUAJM51K3M5OMD8",
               "name":"Form Team",
               "order":1,
               "type":"REGULAR"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"J1L4NVT9IL40J2L4N01K",
                     "name":"Problem Description"
                  }
               ],
               "guid":"L3N6PXVBKN62L4N6PNE3",
               "name":"Problem Description",
               "order":2,
               "type":"REGULAR"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"K2M5OWUAJM51K3M5O12L",
                     "name":"Serial Number(s) of Nonconforming Parts"
                  },
                  {  
                     "guid":"L3N6PXVBKN62L4N6P23P",
                     "name":"Inventory Impact?"
                  },
                  ...
               ],
               "guid":"M4O7QYWCLO73M5O7QOFJ",
               "name":"Immediate Containment",
               "order":3,
               "type":"REGULAR"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"Q8SBU20GPSB7Q9SBU78L",
                     "name":"Possible Causes"
                  },
                  {  
                     "guid":"R9TCV31HQTC8RATCV891",
                     "name":"5 Whys"
                  },
                  ...
               ],
               "guid":"N5P8RZXDMP84N6P8RPGH",
               "name":"Root Cause Analysis",
               "order":4,
               "type":"REGULAR"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"TBVEX53JSVEATCVEXABV",
                     "name":"Corrective Action"
                  }
               ],
               "guid":"P7RAT1ZFORA6P8RATRHW",
               "name":"Corrective Action Plans",
               "order":5,
               "type":"REGULAR"
            },
            {  
               "allowOwnerToAddApprovers":true,
               "approvers":[  
                  {  
                     "fullName":"Dhana Prakash"
                  },
                  {  
                     "fullName":"Heidi Walker"
                  }
               ],
               "guid":"GNFSTNO51TW4EJ211ZCW",
               "name":"Corrective Action Plan Approval",
               "order":6,
               "type":"SIGNOFF"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"UCWFY64KTWFBUDWFYBCW",
                     "name":"Implemented?"
                  },
                  ...
               ],
               "guid":"Q8SBU20GPSB7Q9SBUSI4",
               "name":"Implement and Verify Corrective Actions",
               "order":7,
               "type":"REGULAR"
            },
            {  
               "attributes":[  
                  {  
                     "guid":"XFZI197NWZIEXGZI1EF1",
                     "name":"Preventive Action"
                  },
                  {  
                     "guid":"UCWFY64KTWFBUDWFYBCW",
                     "name":"Implemented?"
                  },
                  ...
               ],
               "guid":"R9TCV31HQTC8RATCVTJB",
               "name":"Prevent Recurrence",
               "order":8,
               "type":"REGULAR"
            },
            {  
               "allowOwnerToAddApprovers":null,
               "approvers":null,
               "attributes":[  
                  {  
                     "guid":"1J3M5DBR03MI1K3M5II4",
                     "name":"Lessons Learned"
                  }
               ],
               "guid":"SAUDW42IRUD9SBUDWUK3",
               "name":"Closure and Team Celebration",
               "order":9,
               "type":"REGULAR"
            }
         ]
      },
      ...
   ],
}
```
Get all active Quality Process templates



GET /settings/qualityprocesses/templates?active=true

```
{
    "count": 2,
    "results": [
        {
            "active": true,
            "creationDateTime": "2014-08-12T22:30:52Z",
            "creator": {
                "email": "cagustin@ptc.com",
                "fullName": "Cole Agustin",
                "guid": "L3N6B03K0R8RATCVDVBM"
            },
            "defaultNumberFormat": null,
            "defaultOwner": null,
            "description": null,
            "guid": "J1L49Y1IYP84N6P821H4",
            "name": "Corrective Action Report (CAR) Template",
            "numberFormats": null,
            "shortName": "CAR",
            "steps": [
                {
                    "attributes": [
                        {
                            "apiName": "VDXGLADUA1I0J2L4J87T",
                            "fieldType": null,
                            "guid": "VDXGLADUA1I0J2L4J87T",
                            "name": "Problem Description",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "K2M5AZ2JZQ95O7Q932IH",
                    "name": "Problem Description",
                    "order": 1,
                    "type": "REGULAR"
                },
                {
                    "attributes": [
                        {
                            "apiName": "WEYHMBEVB2J1K3M5K982",
                            "fieldType": null,
                            "guid": "WEYHMBEVB2J1K3M5K982",
                            "name": "Serial Number(s) of Nonconforming Parts",
                            "value": null
                        },
                        {
                            "apiName": "XFZINCFWC3K2L4N6LA92",
                            "fieldType": null,
                            "guid": "XFZINCFWC3K2L4N6LA92",
                            "name": "Inventory Impact?",
                            "value": null
                        },
                        {
                            "apiName": "YG0JODGXD4L3M5O7MBA5",
                            "fieldType": null,
                            "guid": "YG0JODGXD4L3M5O7MBA5",
                            "name": "Inventory Impact description",
                            "value": null
                        },
                        {
                            "apiName": "ZH1KPEHYE5M4N6P8NCB2",
                            "fieldType": null,
                            "guid": "ZH1KPEHYE5M4N6P8NCB2",
                            "name": "Supplier Containment actions required",
                            "value": null
                        },
                        {
                            "apiName": "0I2LQFIZF6N5O7Q9ODCI",
                            "fieldType": null,
                            "guid": "0I2LQFIZF6N5O7Q9ODCI",
                            "name": "Internal Containment actions required",
                            "value": null
                        },
                        {
                            "apiName": "1J3MRGJ0G7O6P8RAPEDI",
                            "fieldType": null,
                            "guid": "1J3MRGJ0G7O6P8RAPEDI",
                            "name": "Customer Containment actions required",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "L3N6B03K0RA6P8RA43J8",
                    "name": "Immediate Containment",
                    "order": 2,
                    "type": "REGULAR"
                },
                {
                    "attributes": [
                        {
                            "apiName": "2K4NSHK1H8P7Q9SBQFEG",
                            "fieldType": null,
                            "guid": "2K4NSHK1H8P7Q9SBQFEG",
                            "name": "Possible Causes",
                            "value": null
                        },
                        {
                            "apiName": "3L5OTIL2I9Q8RATCRGFE",
                            "fieldType": null,
                            "guid": "3L5OTIL2I9Q8RATCRGFE",
                            "name": "5 Whys",
                            "value": null
                        },
                        {
                            "apiName": "4M6PUJM3JAR9SBUDSHGI",
                            "fieldType": null,
                            "guid": "4M6PUJM3JAR9SBUDSHGI",
                            "name": "Escape Point",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "M4O7C14L1SB7Q9SB54K1",
                    "name": "Root Cause Analysis",
                    "order": 3,
                    "type": "REGULAR"
                },
                {
                    "allowOwnerToAddApprovers": true,
                    "approvers": [
                        {
                            "email": "hwalker@everyroadgps.com",
                            "fullName": "Heidi Walker",
                            "guid": "9RBUZOR8OFWFYH0JSIPJ"
                        },
                        {
                            "email": "jdeckard@everyroadgps.com",
                            "fullName": "James Deckard",
                            "guid": "6O8RWLO5LCTCVEXGGMZQ"
                        },
                        {
                            "email": "jparker@everyroadgps.com",
                            "fullName": "John Parker",
                            "guid": "BTDW1QTAQHYH0J2LLR4L"
                        }
                    ],
                    "defaultApprovers": {
                        "userGroups": null,
                        "users": [
                            {
                                "email": "hwalker@everyroadgps.com",
                                "fullName": "Heidi Walker",
                                "guid": "9RBUZOR8OFWFYH0JSIPJ"
                            },
                            {
                                "email": "jdeckard@everyroadgps.com",
                                "fullName": "James Deckard",
                                "guid": "6O8RWLO5LCTCVEXGGMZQ"
                            },
                            {
                                "email": "jparker@everyroadgps.com",
                                "fullName": "John Parker",
                                "guid": "BTDW1QTAQHYH0J2LLR4L"
                            }
                        ]
                    },
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "CUEX2RUBRI1XGZI1VUAJ",
                    "name": "Corrective Action Plan Approved?",
                    "order": 4,
                    "type": "SIGNOFF"
                },
                {
                    "attributes": [
                        {
                            "apiName": "6O8RWLO5LCTBUDWFUJHF",
                            "fieldType": null,
                            "guid": "6O8RWLO5LCTBUDWFUJHF",
                            "name": "Corrective Action",
                            "value": null
                        },
                        {
                            "apiName": "7P9SXMP6MDUCVEXGVKID",
                            "fieldType": null,
                            "guid": "7P9SXMP6MDUCVEXGVKID",
                            "name": "Implemented?",
                            "value": null
                        },
                        {
                            "apiName": "EWGZ4TWDTK1J2L4N2RP6",
                            "fieldType": null,
                            "guid": "EWGZ4TWDTK1J2L4N2RP6",
                            "name": "Implementation details",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "N5P8D25M2TC8RATC65LC",
                    "name": "Corrective Action",
                    "order": 5,
                    "type": "REGULAR"
                },
                {
                    "attributes": [
                        {
                            "apiName": "ASCV0PS9PGXFYH0JYNLJ",
                            "fieldType": null,
                            "guid": "ASCV0PS9PGXFYH0JYNLJ",
                            "name": "Preventive Action",
                            "value": null
                        },
                        {
                            "apiName": "7P9SXMP6MDUCVEXGVKID",
                            "fieldType": null,
                            "guid": "7P9SXMP6MDUCVEXGVKID",
                            "name": "Implemented?",
                            "value": null
                        },
                        {
                            "apiName": "EWGZ4TWDTK1J2L4N2RP6",
                            "fieldType": null,
                            "guid": "EWGZ4TWDTK1J2L4N2RP6",
                            "name": "Implementation details",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "O6Q9E36N3UD9SBUD76MV",
                    "name": "Preventive Action",
                    "order": 6,
                    "type": "REGULAR"
                }
            ]
        },
        {
            "active": true,
            "creationDateTime": "2014-08-12T22:30:52Z",
            "creator": {
                "email": "cagustin@ptc.com",
                "fullName": "Cole Agustin",
                "guid": "L3N6B03K0R8RATCVDVBM"
            },
            "defaultNumberFormat": null,
            "defaultOwner": null,
            "description": null,
            "guid": "P7RAF47O4VEATCVE87NX",
            "name": "Nonconforming Materials Report (NCMR) Template",
            "numberFormats": null,
            "shortName": "NCMR",
            "steps": [
                {
                    "attributes": [
                        {
                            "apiName": "FXH05UXEUL2K3M5O3SQ8",
                            "fieldType": null,
                            "guid": "FXH05UXEUL2K3M5O3SQ8",
                            "name": "Part Number",
                            "value": null
                        },
                        {
                            "apiName": "GYI16VYFVM3L4N6P4TRB",
                            "fieldType": null,
                            "guid": "GYI16VYFVM3L4N6P4TRB",
                            "name": "Part Name",
                            "value": null
                        },
                        {
                            "apiName": "HZJ27WZGWN4M5O7Q5US5",
                            "fieldType": null,
                            "guid": "HZJ27WZGWN4M5O7Q5US5",
                            "name": "Supplier",
                            "value": null
                        },
                        {
                            "apiName": "I0K38X0HXO5N6P8R6VTB",
                            "fieldType": null,
                            "guid": "I0K38X0HXO5N6P8R6VTB",
                            "name": "Supplier Part Number",
                            "value": null
                        },
                        {
                            "apiName": "J1L49Y1IYP6O7Q9S7WUA",
                            "fieldType": null,
                            "guid": "J1L49Y1IYP6O7Q9S7WUA",
                            "name": "Lot Number(s)",
                            "value": null
                        },
                        {
                            "apiName": "WEYHMBEVB2J1K3M5K982",
                            "fieldType": null,
                            "guid": "WEYHMBEVB2J1K3M5K982",
                            "name": "Serial Number(s) of Nonconforming Parts",
                            "value": null
                        },
                        {
                            "apiName": "K2M5AZ2JZQ7P8RAT8XVI",
                            "fieldType": null,
                            "guid": "K2M5AZ2JZQ7P8RAT8XVI",
                            "name": "Description of Nonconformance",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "Q8SBG58P5WFBUDWF98OM",
                    "name": "Nonconformance Description",
                    "order": 1,
                    "type": "REGULAR"
                },
                {
                    "attributes": [
                        {
                            "apiName": "L3N6B03K0R8Q9SBU9YWA",
                            "fieldType": null,
                            "guid": "L3N6B03K0R8Q9SBU9YWA",
                            "name": "Action",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "R9TCH69Q6XGCVEXGA9P2",
                    "name": "Action Taken",
                    "order": 2,
                    "type": "REGULAR"
                },
                {
                    "attributes": [
                        {
                            "apiName": "M4O7C14L1S9RATCVAZXO",
                            "fieldType": null,
                            "guid": "M4O7C14L1S9RATCVAZXO",
                            "name": "Permanent Correction needed?",
                            "value": null
                        },
                        {
                            "apiName": "N5P8D25M2TASBUDWB0YM",
                            "fieldType": null,
                            "guid": "N5P8D25M2TASBUDWB0YM",
                            "name": "Corrective Action number(s)",
                            "value": null
                        }
                    ],
                    "defaultAssignees": null,
                    "description": null,
                    "guid": "SAUDI7AR7YHDWFYHBAQC",
                    "name": "Corrective Action",
                    "order": 3,
                    "type": "REGULAR"
                }
            ]
        }
    ]
}

```
Get a single Quality Process Template



GET /settings/qualityprocesses/templates/GNFSTNO51TW4EJ211ZCW

```
{  
   "active":true,
   "creationDateTime":"2015-12-14T19:49:08Z",
   "creator":{  
      "fullName":"Cole Agustin"
   },
   "defaultNumberFormat":{  
      "guid":"YG0J2A8OX0JSBUDWFUYM"
   },
   "defaultOwner":{  
      "fullName":"Roy Stafford",
      "guid":"GY116WXX6DUDWFYHPRY3"
   },
   "description":"Eight Discipline (8D)",
   "guid":"HZJ2LTR7GJ2YH0J2LJAP",
   "name":"Eight Discipline (8D) Template",
   "numberFormats":[  
      {  
         "guid":"YG0J2A8OX0JSBUDWFUYM",
         "lastUsed":null,
         "prefixes":[  
            {  
               "guid":"SAUDW42IRUCWFYH0JYZ4",
               "value":"8D-"
            }
         ]
      }
   ],
   "shortName":"8D",
   "steps":[  
      {  
         "attributes":[  
            {  
               "guid":"I0K3MUS8HK3ZI1K3MZ01",
               "name":"Team Members"
            }
         ],
         "guid":"K2M5OWUAJM51K3M5OMD8",
         "name":"Form Team",
         "order":1,
         "type":"REGULAR"
      },
      {  
         "attributes":[  
            {  
               "guid":"J1L4NVT9IL40J2L4N01K",
               "name":"Problem Description"
            }
         ],
         "guid":"L3N6PXVBKN62L4N6PNE3",
         "name":"Problem Description",
         "order":2,
         "type":"REGULAR"
      },
      {  
         "attributes":[  
            {  
               "guid":"K2M5OWUAJM51K3M5O12L",
               "name":"Serial Number(s) of Nonconforming Parts"
            },
            {  
               "guid":"L3N6PXVBKN62L4N6P23P",
               "name":"Inventory Impact?"
            },
            ...
         ],
         "guid":"M4O7QYWCLO73M5O7QOFJ",
         "name":"Immediate Containment",
         "order":3,
         "type":"REGULAR"
      },
      {  
         "attributes":[  
            {  
               "guid":"Q8SBU20GPSB7Q9SBU78L",
               "name":"Possible Causes"
            },
            {  
               "guid":"R9TCV31HQTC8RATCV891",
               "name":"5 Whys"
            },
            ...
         ],
         "guid":"N5P8RZXDMP84N6P8RPGH",
         "name":"Root Cause Analysis",
         "order":4,
         "type":"REGULAR"
      },
      {  
         "attributes":[  
            {  
               "guid":"TBVEX53JSVEATCVEXABV",
               "name":"Corrective Action"
            }
         ],
         "guid":"P7RAT1ZFORA6P8RATRHW",
         "name":"Corrective Action Plans",
         "order":5,
         "type":"REGULAR"
      },
      {  
         "allowOwnerToAddApprovers":true,
         "approvers":[  
            {  
               "fullName":"Dhana Prakash"
            },
            {  
               "fullName":"Heidi Walker"
            }
         ],
         "guid":"GNFSTNO51TW4EJ211ZCW",
         "name":"Corrective Action Plan Approval",
         "order":6,
         "type":"SIGNOFF"
      },
      {  
         "attributes":[  
            {  
               "guid":"UCWFY64KTWFBUDWFYBCW",
               "name":"Implemented?"
            },
            ...
         ],
         "guid":"Q8SBU20GPSB7Q9SBUSI4",
         "name":"Implement and Verify Corrective Actions",
         "order":7,
         "type":"REGULAR"
      },
      {  
         "attributes":[  
            {  
               "guid":"XFZI197NWZIEXGZI1EF1",
               "name":"Preventive Action"
            },
            {  
               "guid":"UCWFY64KTWFBUDWFYBCW",
               "name":"Implemented?"
            },
            ...
         ],
         "guid":"R9TCV31HQTC8RATCVTJB",
         "name":"Prevent Recurrence",
         "order":8,
         "type":"REGULAR"
      },
      {  
         "allowOwnerToAddApprovers":null,
         "approvers":null,
         "attributes":[  
            {  
               "guid":"1J3M5DBR03MI1K3M5II4",
               "name":"Lessons Learned"
            }
         ],
         "guid":"SAUDW42IRUD9SBUDWUK3",
         "name":"Closure and Team Celebration",
         "order":9,
         "type":"REGULAR"
      }
   ]
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
