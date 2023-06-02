# POST Change Status (Submitting and Auto-Routing)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This article demonstates how to submit a change that has a routing method of auto-routing. Auto-Routing routing methods can be configured within the Configuration, Changes view in Workspace settings or in the Routing section of the specific change category in the Changes, Category view in workspace settings.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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

## Sample Requests and Responses
Submits a Change when the routing method is set to auto-routing. In this scenario, no routing is applied and the routing method is set to auto-routing so the change is effective immediately after submitting.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "L3N6P2NE14NQ9R77AYVQ"
    },
    "comment": "Submitting for approval without a routing in an auto-routing configuraiton workspace",
    "status": "SUBMITTED"
}
```
**Response** 

```
{
    "change": {
        "guid": "L3N6P2NE14NQ9R77AYVQ",
        "number": "ECO-000023"
    },
    "comment": "Unlocking Change to edit routing and description.",
    "status": "EFFECTIVE",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/9E97F4657967ECPDMS",
           "app": "https://app.bom.com/9E97F4657967ECPDMS"

   }
}
```
Submits a Change when the routing method is set to auto-routing. In this scenario, a routing is specified within the workspace configuration settings or within the Routing tab for the change category.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "L3N6P2NE14NQ9R77AYVQ"
    },
    "comment": "Submitting for approval. Routing is specified by the modifications of the Item within the change.",
    "status": "SUBMITTED"
}
```
**Response** 

```
{
    "change": {
        "guid": "L3N6P2NE14NQ9R77AYVQ",
        "number": "ECO-000023"
    },
    "comment": "Submitting for approval. Routing is specified by the modifications of the Item within the change.",
    "status": "SUBMITTED_FOR_APPROVAL",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/BC715466F5504BF1BD",
           "app": "https://app.bom.com/BC715466F5504BF1BD"

   }
}
```
Returns an error if a user includes a change administrator when the change has a routing method of auto-routing.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "L3N6P2NE14NQ9R77AYVQ"
    },
    "administrators": {
        {
           "guid": "WEYH0DYPCFWFYH0JSIPD"
        }
    },
    "comment": "Submitting for approval using a Change with a category specific routing set to auto-routing",
    "status": "SUBMITTED"
}
```
**Response** 

```
{
    "status": 400,
    "errors": [
        {
            "code": 3145,
            "message": "This specific change lifecycle transition does not support the inclusion of a change administrator."
        }
    ]
}
```
