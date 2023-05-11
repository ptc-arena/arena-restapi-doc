# POST Change Status (Submitting and User-Defined)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This article demonstates how to submit a change that has a routing method of user\-defined. User\-Defined routing methods can be configured within the Configuration, Changes view in Workspace settings or in the Routing section of the specific change category in the Changes, Category view in workspace settings.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Requests and Responses
Submits a Change when the routing method is set to user\-defined. In this scenario, the routing is configured by the user in the user interface.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "R9TCV8TK7ATWFXDDG41X"
    },
    "comment": "Submitting Change for Approval. User defined routing method. Routing specified.",
    "status": "SUBMITTED"
}
```


```
{  
    "change": {
        "guid": "R9TCV8TK7ATWFXDDG41X",
        "number": "ECO-000028"
    },
    "comment": "Submitting Change for Approval. User defined routing method. Routing specified.",
    "status": "SUBMITTED_FOR_APPROVAL"
}
```
Returns an error if the user submits the change and no routing is specified.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "R9TCV8TK7ATWFXDDG41X"
    },
    "comment": "Submitting Change for Approval. User defined routing method. No routing specified.",
    "status": "SUBMITTED"
}
```


```
{
     "status": 400,
     "errors": [
         {
             "code": 5006,
             "message": "No routing has been specified for this Change. The Change configuration for this workspace requires that at least one routing be 
                 assigned before a Change may be submitted."
         },
         {
             "code": 5106,
             "message": "Item Number #347-98765: The modified Item has required inventory disposition actions that must be selected. Before this Change can 
                 be submitted you must fo to the Inventory Disposition subview of the Items view and select a Disposition Action for each required Disposition 
                 Status."
         },
         {
             "code": 5183,
             "message": "Item Number #450-98900: The modified Item is being released to Design and may not contain this unreleased Item in its BOM. You must 
                 remove the Unreleased Item from the BOM of the modified Item, release it to Design (by including it in this Change), or remove the modified
                 Item from this Change. If you choose to include this Item in this Change, it will be released to the Design stage at the same phase as the 
                 modified Item."
         },
         {
             "code": 5202,
             "message": "Notice: No approval deadline has been specified for this Change."
         }
     ] 
}
```
