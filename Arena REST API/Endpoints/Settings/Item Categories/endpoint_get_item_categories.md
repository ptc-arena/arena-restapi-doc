# GET Item Categories


/settings/items/categories



/settings/items/categories/&lt;GUID&gt;

This returns   objects available for Items. Appending a  GUID to the URL returns the Category with that GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Parameters

| Name | Value | Description |
|  --- |  --- |  --- | 
| path | string | This is used to filter out categories. The root of path for item is "item". If you want to get all the categories under the root category which start with A, you can send a request as , where "\" is the separator between parent category and child category.  |
| includeDeleted | Boolean | This is used to include deleted Categories. If includeDeleted is true, then deleted Categories will be included in the results. If includeDeleted is false, then deleted Categories will not be included in the results. Omitting the includeDeleted parameter altogether in this call will also exclude deleted Categories from the results. |

api.arenasolutions.com/items/categories? path=item\A\*

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all non\-deleted  item categories



GET /settings/items/categories

```
{  
   "count":70,
   "results":[  
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2008-03-04T20:04:47Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":"Item is a system-defined category",
         "guid":"0I2LQGHHQXGQ9S4C0TYC",
         "level":1,
         "name":"Item",
         "parentCategory":{
             "guid": "L3N6B134HGZ9SBNVJQVC"
         },
         "path":"Item",
         "requirements":[  
            {  
               "evidenceType":"DIRECT_FILES",
               "mark":null,
               "rationale":null,
               "requirement":{  
                  "guid":"EWGZIQXJZ7PP8RASY3JE",
                  "name":"api-requirement1"
               },
               "status":"EXEMPT"
            },
            {  
               "evidenceType":"AML_AND_FILES",
               "mark":"dd Compliance Mark 2",
               "rationale":"dd Rationale 2",
               "requirement":{  
                  "guid":"M4O7QY5R7FXXGZI07XHU",
                  "name":"RoHS (2002/95/EC)"
               },
               "status":"UNKNOWN"
            }
         ],
         "structural": false,
         "systemDefined": true
      },
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2008-03-05T13:26:37Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":null,
         "guid":"DVFY3TUU3AT3M5HPD6CB",
         "level":2,
         "name":"Document",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "parentCategory":{
             "guid": "Z9Q49PGTY8659JHSN"
         },
         "path":"Item\Document",
         "structural": false,
         "systemDefined": false
      },
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2010-09-05T15:45:31Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":null,
         "guid":"I0K38Y01EDW6P8KSGNS2",
         "level":3,
         "name":"Artwork - SmartHOME",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "path":"Item\Document\Artwork",
         "parentCategory": {
             "guid": "ADT9879H3W6182WND"
         },
         "requirements":[],
         "structural": false,
         "systemDefined": false
      },
      ...
   ]
}
```
Get all item categories including deleted categories



GET settings/items/categories?includeDeleted=true

```
{  
   "count":98,
   "results":[  
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2008-03-04T20:04:47Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":"Item is a system-defined category",
         "guid":"0I2LQGHHQXGQ9S4C0TYC",
         "level":1,
         "name":"Item",
         "parentCategory":{
             "guid": "L3N6B134HGZ9SBNVJQVC"
         },
         "path":"Item",
         "requirements":[  
            {  
               "evidenceType":"DIRECT_FILES",
               "mark":null,
               "rationale":null,
               "requirement":{  
                  "guid":"EWGZIQXJZ7PP8RASY3JE",
                  "name":"api-requirement1"
               },
               "status":"EXEMPT"
            },
            {  
               "evidenceType":"AML_AND_FILES",
               "mark":"dd Compliance Mark 2",
               "rationale":"dd Rationale 2",
               "requirement":{  
                  "guid":"M4O7QY5R7FXXGZI07XHU",
                  "name":"RoHS (2002/95/EC)"
               },
               "status":"UNKNOWN"
            }
         ],
         "structural": false,
         "systemDefined": true
      },
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2008-03-05T13:26:37Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":null,
         "guid":"DVFY3TUU3AT3M5HPD6CB",
         "level":2,
         "name":"Document",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "parentCategory":{
             "guid": "Z9Q49PGTY8659JHSN"
         },
         "path":"Item\Document",
         "structural": false,
         "systemDefined": false
      },
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2010-09-05T15:45:31Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":null,
         "guid":"I0K38Y01EDW6P8KSGNS2",
         "level":3,
         "name":"Artwork - SmartHOME",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "path":"Item\Document\Artwork",
         "parentCategory": {
             "guid": "ADT9879H3W6182WND"
         },
         "requirements":[],
         "structural": false,
         "systemDefined": false
      },
      {  
         "activated":true,
         "assignable":false,
         "creationDateTime":"2008-03-05T13:27:31Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "deletionDateTime": "2020-08-25T18:45:40Z",
         "description":null,
         "guid":"M4O7C233CJ2CVEQYMFLW",
         "level":3,
         "name":"Artwork-Chi",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "path":"Item\Document\Artwork-Chi",
         "parentCategory": {
             "guid": "ADT9879H3W6182WND"
         },
         "requirements":[],
         "structural": false,
         "systemDefined": false
      },
       {  
         "activated":true,
         "assignable":false,
         "creationDateTime":"2020-09-11T05:38:59Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "deletionDateTime": "2020-09-11T05:40:23Z",
         "description":null,
         "guid":"SAUDI7B9E3K3M5O784TO",
         "level":3,
         "name":"Artwork-SF",
         "numberFormat":{  
            "guid":"P7Q9SBU3M5LMFGCG"
         },
         "path":"Item\Document\Artwork-SF",
         "parentCategory": {
             "guid": "ADT9879H3W6182WND"
         },
         "requirements":[],
         "structural": false,
         "systemDefined": false
      },
      ...
   ]
}
```
Get all item categories that begin with A



GET settings/items/categories?path=item\A

```
{  
   "count":6,
   "results":[  
      {  
         "activated":true,
         "assignable":false,
         "creationDateTime":"2011-02-05T01:05:49Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":null,
         "guid":"ZH1K3BKKHYHRATCTHTHN",
         "level":2,
         "name":"Assembly",
         "numberFormat":{  
            "guid":"VDXGZ7GGDUDM5O7OL7R3"
         },
         "path":"Item\Assembly",
         "parentCategory": {
             "guid": "K2M5A023GFY8RAMUIPU5"
         },
         "requirements":[],
         "structural": false,
         "systemDefined":false
      },
      {  
         "activated":true,
         "assignable":true,
         "creationDateTime":"2011-02-05T01:06:44Z",
         "creator":{  
            "email": "hwalker@everyroadgps.com",
            "fullName":"Heidi Walker",
            "guid": "4M6P8GPPM3K3M507QMJ9"
         },
         "description":"Shippable ERGPS Product Assemblies",
         "guid":"0I2L4CLLIZISBUDUIUI5",
         "level":3,
         "name":"Finished Good",
         "numberFormat":{  
            "guid":"VDXGZ7GGDUDM5O7OL7R3"
         },
         "path":"Item\Assembly\Finished Good",
         "parentCategory": {
             "guid": "EWGZ4UWXA9S2L4G0CJNL"
         },
         "requirements":[],
         "structural": false,
         "systemDefined":false
      },
      ...
   ]
}
```
Get a single item category



GET /settings/items/categories/UCWFKABBKRAK3MY6UNTU

```
{  
   "activated":true,
   "assignable":true,
   "creationDateTime":"2008-03-04T22:56:04Z",
   "creator":{  
      "email": "hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid": "4M6P8GPPM3K3M507QMJ9"
   },
   "description":null,
   "guid":"UCWFKABBKRAK3MY6UNTU",
   "level":4,
   "name":"Printed Circuit Board Assembly",
   "numberFormat":{  
      "guid":"N5O7Q9S1K3JKDEAJ"
      "fields": [
          {
            "guid": "M4O7LIMOZGXK3M4CZINO",
            "value": "110"
          },
          {
            "guid": "VDXGURVX8P8EXGL9SY9Q",
            "value": "-5"
          }
      ],    
   },
   "path":"Item\Part\Assembly\Printed Circuit Board Assembly",
   "parentCategory": {
             "guid": "ZH1KPFHIVUBUDWFYUEB"
         },
   "requirements":[],
   "structural": false,
   "systemDefined":false
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
