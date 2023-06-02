# GET Change Categories
/settings/changes/categories

/settings/changes/categories/&lt;GUID&gt;

Returns Categories available for Changes. Appending a GUID to the URL returns the category with that GUID.

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
Get all change categories

GET /settings/changes/categories

```
{
   "count":9,
   "results":[
      {
         "activated":true,
         "allowDuplicateRevisions":true,
         "allowManualRevisionEntry":true,
         "assignable":true,
         "creationDateTime":"2011-01-05T00:26:30Z",
         "creator":{
            "email":"cvickery@arenasolutions.com",
            "fullName":"Chris Vickery",
            "guid":"VDXGZ7GGDUBUDWFYHI7P"
         },
         "description":"Change is a system-defined category",
         "effectivityType":null,
         "enforceDefaultEffectivityType":false,
         "enforceDefaultNumberSequence":false,
         "guid":"SAUDW4DDARAK3M5MAMDU",
         "initialImplementationStatus":null,
         "level":1,
         "name":"Change",
         "numberingSequencePrefixDefault":null,
         "path":"Change",
         "systemDefined":true
      },
      {
         "activated":true,
         "allowDuplicateRevisions":true,
         "allowManualRevisionEntry":true,
         "assignable":false,
         "creationDateTime":"2011-02-08T22:08:49Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"4M6P8GPPM3K3M5O7QMJ9"
         },
         "description":null,
         "effectivityType":"PERMANENT_ON_APPROVAL",
         "enforceDefaultEffectivityType":false,
         "enforceDefaultNumberSequence":false,
         "guid":"Q8SBU2BB8P8I1K3K8KBY",
         "initialImplementationStatus":"BLANK",
         "level":2,
         "name":"Change Order",
         "numberingSequencePrefixDefault":null,
         "path":"Change\\Change Order",
         "systemDefined":false
      },
      {
         "activated":true,
         "allowDuplicateRevisions":true,
         "allowManualRevisionEntry":true,
         "assignable":true,
         "creationDateTime":"2011-02-08T22:09:30Z",
         "creator":{
            "email":"hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid":"4M6P8GPPM3K3M5O7QMJ9"
         },
         "description":null,
         "effectivityType":"PERMANENT_ON_APPROVAL",
         "enforceDefaultEffectivityType":true,
         "enforceDefaultNumberSequence":true,
         "guid":"R9TCV3CC9Q9J2L4L9LC9",
         "initialImplementationStatus":"NOT_STARTED",
         "level":3,
         "name":"Compliance Change Order",
         "numberingSequencePrefixDefault":{
            "guid":"FXH0JR00XEVSBUDUTRCG",
            "value":"CCO-"
         },
         "path":"Change\\Change Order\\Compliance Change Order",
         "systemDefined":false
      },
      ...
   ]
}
```
Get a Change category with a specific GUID

GET /settings/changes/categories/guid

```
{
   "activated":true,
   "allowDuplicateRevisions":true,
   "allowManualRevisionEntry":true,
   "assignable":true,
   "creationDateTime":"2011-02-08T22:09:30Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "description":null,
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "enforceDefaultEffectivityType":true,
   "enforceDefaultNumberSequence":true,
   "guid":"R9TCV3CC9Q9J2L4L9LC9",
   "initialImplementationStatus":"NOT_STARTED",
   "level":3,
   "name":"Compliance Change Order",
   "numberingSequencePrefixDefault":{
      "guid":"FXH0JR00XEVSBUDUTRCG",
      "value":"CCO-"
   },
   "path":"Change\\Change Order\\Compliance Change Order",
   "systemDefined":false
}
```
