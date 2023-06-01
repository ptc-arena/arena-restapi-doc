# POST Change Status (Submitting and Admin-Defined)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This article demonstates how to submit a change that has a routing method of admin-defined. Admin-Defined routing methods can be configured within the Configuration, Changes view in Workspace settings or in the Routing section of the specific change category in the Changes, Category view in workspace settings.

The Admin-Defined routing method is unique because it is a two-setp submission process. A user must first submit the change to a change administrator. This process is called submitted for routing. The change administrator then assigns a routing to the change and submits the change. This process is called submitted for approval.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Requests and Responses
Submits a change for routing when routing method is set to admin-defined. In this endpoint, the user submits the change for routing. In the example below, the user doesn't have to define the change administrator since it is defined by the change category.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP"
    },
    "administrators": {
        {
           "guid": "J1L4N0LCZ2J2L4N6F6ZL"
        }
    },
    "comment": "Change was built with a category that contains an admin defined routing method. Modifying to a different Change Admin",
    "status": "SUBMITTED"
}
```
**Response** 

```
{
    "administrators": [
        {
        "email": "hwalker@everyroadgps.com"
        "number": "Heidi Walker"
        "guid": "WEYH0DYPCFWFYH0JSIPD",
        },
    ],    
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP",
        "number": "ECO-000027"
    },
    "comment": "Change was built with a category that contains an admin defined routing method.",
    "status": "SUBMITTED_FOR_ROUTING",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/A3FE5DD85583420B83",
           "app": "https://app.bom.com/A3FE5DD85583420B83"

   }
}
```
POST /changes/statuschanges

Submits a change for routing when routing method is set to admin-defined. In this endpoint, the user submits the change for routing. In the example below, the user includes a change administrator to modify the assigned change administrator for the change.

**Request** 

```
{
    "administrators": [
        {
        "email": "tmakamuri@everyroadgps.com"
        "number": "Toshiro Makamuri"
        "guid": "J1L4N0LCZ2J2L4N6F6ZL",
        },
    ],    
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP",
        "number": "ECO-000027"
    },
    "comment": "Change was built with a category that contains an admin defined routing method. Modifying to a different Change Admin",
    "status": "SUBMITTED_FOR_ROUTING"
}
```
**Response** 

```
{
    "administrators": [
        {
        "email": "tmakamuri@everyroadgps.com"
        "number": "Toshiro Makamuri"
        "guid": "J1L4N0LCZ2J2L4N6F6ZL",
        },
    ],    
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP",
        "number": "ECO-000027"
    },
    "comment": "Change was built with a category that contains an admin defined routing method. Modifying to a different Change Admin",
    "status": "SUBMITTED_FOR_ROUTING",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/FF1DF627041A4CDLPD",
           "app": "https://app.bom.com/FF1DF627041A4CDLPD"

    }   
}
```
POST /changes/statuschanges

In this example, a change administrator submits a change that has been submitted for routing. It is implied that the change administrator has assigned a routing through the use of another endpoint. Once the routing is configured and the change administrator submits the change, the change moves to the following status: SUBMITTED_FOR_APPROVAL.

**Request** 

```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP"
    },
    "comment": "Submitting Change for Approval. The user performing this call is the Change Administrator",
    "status": "SUBMITTED"
}
```
**Response** 

```
{
    "administrators": [
        {
        "email": "tmakamuri@everyroadgps.com"
        "number": "Toshiro Makamuri"
        "guid": "J1L4N0LCZ2J2L4N6F6ZL",
        },
    ],    
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP",
        "number": "ECO-000027"
    },
    "comment": "Submitting Change for Approval. The user performing this call is the Change Administrator",
    "status": "SUBMITTED_FOR_APPROVAL",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/23A808129C5E4A009F",
           "app": "https://app.bom.com/23A808129C5E4A009F"

    } 
}
```
**Request** 

An error is returned if a user attempts to include a change administrator in the request body for a change with a status of SUBMITTED_FOR_ROUTING. Note that in the earlier example where the user edited the change administrator with this endpoint the change was moving from a status of OPEN_AND_UNLOCKED to SUBMITTED_FOR_ROUTING. In the example below, the change already contains a status of SUBMITTED_FOR_ROUTING.

```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBE2ZP"
    },
    "administrators": {
        {
           "guid": "J1L4N0LCZ2J2L4N6F6ZL"
        }
    },
    "comment": "Change was built with a category that contains an admin defined routing method. Change was already submitted for routing.",
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
