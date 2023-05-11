# POST Item Lifecycle Phase Change


/items/lifecyclephasechanges

Releases a new revision of an item with a given GUID to a target lifecycle phase specified within the request. Returns revision GUIDs for effective, superseded, and working revisions of the item.

The following phase transitions are allowed:

* Release to Design
\(move an unreleased Item to a Design stage lifecycle phase.\)

* Make Effective in Design \(make working modifications effective in a new revision while remaining in the same Design phase.\)


* Release to Production
\(move a Design stage Item to a Production stage lifecycle phase.\)

* Make Effective in Production
\(make working modifications effective in a new revision while remaining in the same Production phase.\)


Of these phase transitions, Release to Design, Make Effective in Design, and Make Effective in Production require the working revision of the item because these endpoints operate on the working revision. Release to Production requires that the item GUID  be the effective revision. The target lifecycle phase can be any defined for the workspace, including custom phases.

This API request can generate  errors, warnings, and notices. The request will fail if there is at least one error or warning.  If the value for “proceedOnNotice” is True, the request will continue if it generates notices.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{  
   "item":{  
      "guid":"Q8SBG677GN6N6LE4IPZ2"
   },
   "proceedOnNotice":true,
   "toLifecyclePhase":{  
      "guid":"K2M5AO11AHZ2L4N6PIZ6"
   },
   "notes":"Ready for release",
   "revisionNumber":"3"
}
```
## Optional Fields

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| proceedOnNotice<br> | true or false<br> | This field, when set to true, forces the operation to continue even if there are errors.<br> |
| notes<br> | string<br> | This field enters a comment in the item record<br> |
| revisionNumber<br> | string<br> | This field specifies a target revision number for the transition. If this field is not included, and a revision sequence is defined for the target lifecycle stage \(and if the current revision number appears in that sequence\) the next revision in the sequence will be selected.\)<br> |

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

## Sample Responses
```
{  
   "effectiveRevItem":{  
      "guid":"M4O7QY5R7FYFYCHZ27X0",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/M4O7QY5R7FYFYCHZ27X0",
          "app": "https://app.arenasolutions.com/M4O7QY5R7FYFYCHZ27X0"        }
   },
   "supersededRevItem":{  
      "guid":"CUEXGOVHX5O5O27PSXND",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/CUEXGOVHX5O5O27PSXND",
          "app": "https://app.arenasolutions.com/CUEXGOVHX5O5O27PSXND"       }
   },
   "workingRevItem":{  
      "guid":"WEYH08F1HP8P8MR9CH77",
      "url": {
          "api": "https://api.arenasolutions.com/v1/items/M4O7QY5R7FYFYCHZ27X0",
          "app": "https://app.arenasolutions.com/M4O7QY5R7FYFYCHZ27X0"       }
   }
}
```
Returns an error if the item GUID is not valid

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
