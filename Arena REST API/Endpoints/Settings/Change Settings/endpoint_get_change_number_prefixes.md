# GET Change Number Prefixes
/settings/changes/numbersequenceprefixes

This returns all  Change Number Prefixes available for the workspace.

Change number formats in Arena consist of a prefix \(such as ECO\) and a six-digit autogenerating sequence \(such as 000001\), separated by a dash.

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
| Content-Length  | number  | number of characters in the response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all change number prefixes

GET /settings/changes/numbersequenceprefixes

```
{
   "count":7,
   "results":[
      {
         "guid":"QCCLWNGXUH1VAQZSV6XB",
         "value":"CCO-"
      }
      {
         "guid":"F54NB3G08DIVT5DZS3FD",
         "value":"DEV-"
      }
      {
         "guid":"T35HQJRC1U0QRCBLHA7C",
         "value":"DCO-"
      }
      {
         "guid":"P7RATAT95I1ATCVEXGWY",
         "value":"ECO-"
      }
      {
         "guid":"G84PT70BWBL2Y8JN4ZS6",
         "value":"MCO-"
      }
      {
         "guid":"RZAMSRGGOK2CIUD3Y3X0",
         "value":"PRO-"
      }
      {
         "guid":"YKIQM9VCSGQ254DJ5VVS",
         "value":"SS-"
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
