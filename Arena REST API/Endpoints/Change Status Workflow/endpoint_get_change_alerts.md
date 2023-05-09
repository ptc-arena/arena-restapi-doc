# GET Change Alerts


changes/&lt;guid&gt;/alerts

Submitting changes can fail due to change submission errors. Change submission errors can occur due to Item lifecycle disagreements, failure to complete required invetory dispositions, and other issues.

When a Change fails to submit, the first 20 errors are displayed within the response. If  there are more than 20 errors, users can use this GET Change Alerts endpoint to see all the errors.

The Change Alerts endpoints displays warning notices as well as errors. Errors are issues that have to be corrected in order for the Change to be submitted. Notices are warning notifications that do not have to be corrected in order for the Change to be submitted.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get the Change Alerts of a Change.



GET /changes/&lt;GUID&gt;/alerts

```
{
     "count": 54,
     "results": [
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
         },
         ...
     ] 
}
```
In the example above, alert  error code 5202 is a notice. All the other alerts that do not contain the string "Notice:" are errors that must be resolved in order for the change to be submitted.

