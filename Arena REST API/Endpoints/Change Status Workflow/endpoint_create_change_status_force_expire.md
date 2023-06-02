# POST Change Status (Force Expire Deviations)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This version of the POST Change Status endpoint demonstates how to force the expiration of a Change with temporary effectivity \(also known as a Deviation\). Only Change Administators can perform this version of the endpoint. 

For changes with temporary effectivity that have reached a status of  EFFECTIVE, a Change administrator can remove the temporary effectivity of the change before its scheduled expiration date by inputting a value of EXPIRED for the attribute status within the request body of the POST Change Status endpoint.

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
For Change administrators, inputting a status of EXPIRED in an effective Change with temporary effectivity forces the deviation to expire before its scheduled date.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "SAUDW9UL8BUXGYEEHF43"
    },
    "comment": "Per management, we're forcing the expiration of DEV-000026.",
    "status": "EXPIRED"
}
```
**Response** 

```
{
    "administrators": [
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        }
    ],
    "change": {
        "guid": "SAUDW9UL8BUXGYEEHF43",
        "number": "ECO-000026"
    },
    "comment": "Per management, we're forcing the expiration of DEV-000026.",
    "status": "EXPIRED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/6FED7D50362782JFBC",
           "app": "https://app.bom.com/6FED7D50362782JFBC"

   }
}
```
