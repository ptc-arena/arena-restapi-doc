# GET Change Routings
/settings/changes/routings

/settings/changes/routings/&lt;GUID&gt;

Returns Routings available for Changes. Appending a GUID to the URL returns the routing with that GUID. 

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
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all change routings

GET /settings/changes/routings

```
{
   "count":4,
   "results":[
      {
         "description":"To be used for all changes where working modifications are being made effective without a phase change.",
         "guid":"J1L4NV441IZ2L4N6P3EZ",
         "name":"Approval Routing"
      },
      {
         "description":null,
         "guid":"L3N6PX663K14N6P8R5GB",
         "name":"CTO Approval Only"
      },
      {
         "description":"To be used for updating sourcing information on parts. Also responsible for part obsolescence.",
         "guid":"K2M5OW552J03M5O7Q4F0",
         "name":"Component Librarian"
      },
      {
         "description":"This routing approves releases to Design or Production",
         "guid":"N5P8RZ885M36P8RAT7H0",
         "name":"Phase Changes"
      }
   ]
}
```
Get a change routing with a specific GUID

GET /settings/changes/routings/GUID

```
{  
   "description":"To be used for updating sourcing information on parts. Also responsible for part obsolescence.",
   "guid":"K2M5OW552J03M5O7Q4F0",
   "name":"Component Librarian"
}
```
