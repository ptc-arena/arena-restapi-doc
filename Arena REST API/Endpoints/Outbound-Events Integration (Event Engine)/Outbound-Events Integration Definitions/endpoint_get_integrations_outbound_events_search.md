# GET Outbound-Events Integrations (Search)


/outboundevents

Returns a collection of outbound event integrations objects matching the given search criteria.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Searchable Attributes

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| enabled<br> | string<br> | Indicates if an Integration is enabled. The value is true if the integration is enabled. The value is false if the integration is disabled.<br> |
| name<br> | string<br> | The name of the outbound integration.<br> |

Search behavior in the Arena REST API differs from search behavior in the Arena application. In the API, a trailing asterisk \(wildcard\) is required to return results that start with a string; in the Arena application, a trailing asterisk is always implied.

GET calls that include Object numbers that include a percentage character, %, must encode the percentage as %25 in order to return results.

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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

## Sample Response Body
Get all outbound event integrations



GET /outboundevents

```
{
    "count": 3,
    "results": [
        {
            "creationDateTime": "2021-07-29T23:00:02Z",
            "creator": {
                "email": "cstone@everyroadgps.com",
                "fullName": "Craig Stone",
                "guid": "FXH0JWH8VYFYH0J25014"
            },
            "enabled": false,
            "guid": "5D2V6J4VILWUDWFYH3FBG",
            "lastModifiedDateTime": "2021-08-01T21:41:31Z",
            "modifyUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "EveryHome Outbound Event Integration Clovex",
            "status": "NEEDS_ATTENTION"
        },
        {
            "creationDateTime": "2021-07-20T23:32:02Z",
            "creator": {
                "email": "cstone@everyroadgps.com",
                "fullName": "Craig Stone",
                "guid": "FXH0JWH8VYFYH0J25014"
            },
            "enabled": true,
            "guid": "2K4N6J4VILWUDWFYH3YT",
            "lastModifiedDateTime": "2021-08-06T21:41:31Z",
            "modifyUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "EveryHome Outbound Event Integration",
            "status": "NEEDS_ATTENTION"
        },
        {
            "creationDateTime": "2021-07-28T12:32:02Z",
            "creator": {
                "email": "cstone@everyroadgps.com",
                "fullName": "Craig Stone",
                "guid": "FXH0JWH8VYFYH0J25014"
            },
            "enabled": false,
            "guid": "M4O7QY5R7FY8RATAYXNX",
            "lastModifiedDateTime": "2021-08-12T21:41:31Z",
            "modifyUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "EveryHome Outbound Event Gamma Integration",
            "status": "NEEDS_ATTENTION"
        }
    ]
}
```
Get outbound events integrations that are enabled



GET &lt;url&gt;/outboundevents?enabled=true

```
{
    "count": 1,
    "results": [
        {
            "creationDateTime": "2021-07-20T23:32:02Z",
            "creator": {
                "email": "cstone@everyroadgps.com",
                "fullName": "Craig Stone",
                "guid": "FXH0JWH8VYFYH0J25014"
            },
            "enabled": true,
            "guid": "2K4N6J4VILWUDWFYH3YT",
            "lastModifiedDateTime": "2021-08-06T21:41:31Z",
            "modifyUser": {
                "email": "hwalker@everyroadgps.com",
                "fullName": "Heidi Walker",
                "guid": "WEYH0DYPCFWFYH0JSIPD"
            },
            "name": "EveryHome Outbound Event Integration",
            "status": "NEEDS_ATTENTION"
        }
    ]
}
```
Request with an invalid search attribute.

GET /outboundevents?transferType=Item Revision

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3003,
         "message":"The value for the attribute \"trasnferType\" is not valid."
      }
   ]
}
```
