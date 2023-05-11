# GET Change Categories


/settings/changes/categories



/settings/changes/categories/&lt;GUID&gt;

Returns  available for Changes. Appending a GUID to the URL returns the category with that GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
