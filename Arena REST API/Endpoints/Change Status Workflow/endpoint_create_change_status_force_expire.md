# POST Change Status (Force Expire Deviations)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to force the expiration of a Change with temporary effectivity \(also known as a Deviation\). Only Change Administators can perform this version of the endpoint. 

For changes with temporary effectivity that have reached a status of  EFFECTIVE, a Change administrator can remove the temporary effectivity of the change before its scheduled expiration date by inputting a value of EXPIRED for the attribute status within the request body of the POST Change Status endpoint.

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
For Change administrators, inputting a status of EXPIRED in an effective Change with temporary effectivity forces the deviation to expire before its scheduled date.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "SAUDW9UL8BUXGYEEHF43"
    },
    "comment": "Per management, we're forcing the expiration of DEV-000026.",
    "status": "EXPIRED"
}
```


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
