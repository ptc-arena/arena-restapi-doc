# GET Item Lifecycle Phases
/settings/items/lifecyclephases

This returns all Item Lifecycle Phases defined for the workspace.

## Reuqest Header

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
Get all item lifecycle phases

GET /settings/items/lifecyclephases

```
{  
   "count":7,
   "results":[  
      {  
         "active":true,
         "guid":"9RBUDLUUR8QTCVEXGVB9",
         "name":"Abandoned",
         "shortName":"Aban",
         "stage":"DESIGN",
         "used":true
      },
      {  
         "active":true,
         "guid":"8QATCKTTQ7PSBUDWFUA1",
         "name":"Deprecated",
         "shortName":"Depr",
         "stage":"PRODUCTION",
         "used":true
      },
      {  
         "active":true,
         "guid":"BTDWFNWWTASVEXGZIXDY",
         "name":"In Design",
         "shortName":"In Des",
         "stage":"DESIGN",
         "used":true
      },
      {  
         "active":true,
         "guid":"K2M5OW552J14N6P8R6JI",
         "name":"Prototype",
         "shortName":"Proto",
         "stage":"DESIGN",
         "used":true
      },
      {  
         "active":true,
         "guid":"ASCVEMVVS9RUDWFYHWC3",
         "name":"In Production",
         "shortName":"In Prod",
         "stage":"PRODUCTION",
         "used":true
      },
      {  
         "active":true,
         "guid":"7P9SBJSSP6ORATCVET9H",
         "name":"Obsolete",
         "shortName":"Obs",
         "stage":"PRODUCTION",
         "used":false
      },
      {  
         "active":true,
         "guid":"6O8RAIRRO5NQ9SBUDS87",
         "name":"Unreleased",
         "shortName":"Unrel",
         "stage":"PRELIMINARY",
         "used":true
      }
   ]
}
```
