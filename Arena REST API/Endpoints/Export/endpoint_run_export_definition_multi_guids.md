# POST Export Run (Multiple Guids)
/exports/&lt;GUID&gt;/runs

By building a criteria that includes multiple GUIDS, users can use the POST Export Run endpoint to export those specific items associated with the GUIDs within the criteria. This variant of the POST Export Run endpoint can be useful in integrations that return item GUIDs..

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
* Run an Export were multiple Item GUIDs are specified in the Criteria.

```
{   
    "criteria": [
        [
            {
                "attribute":"guid",
                "operator":"IS_IN",
                "value": ["CUEXB8CEPGHGZI18WDMU", "M407LIMOZGZQ5TUP27F"]
            }
        [
    ]
}
```
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

## Sample Response Body
Export Run is processing

```
{  
   "completionDateTime":null,  
   "creationDateTime":"2023-03-08T09:32:25Z",
   "creator": {
       "email": "hwalker@everyhome.com",
       "fullName": "Heidi Walker",
       "guid":"ASCV96ACN4L4N6P6BG6H"
   },
   "criteria":[
      {
         "attribute":"guid",
         "value": [
             "CUEXB8CEPGHGZI18WDMU",
             "M407LIMOZGZQ5TUP27F"
         ],
         "operator":"IS_IN"
      }
   ],
   "criteriaResultsCount": 1,
   "guid":"Z8SPLFQS3K0DTYB56MW",
   "number":12,
   "status":"RUNNING"
}
```
Export Run completed

```
{  
   "completionDateTime":"2023-03-08T09:40:00Z",  
   "creationDateTime":"2023-03-08T09:32:25Z",
   "creator": {
       "email": "hwalker@everyhome.com",
       "fullName": "Heidi Walker",
       "guid":"ASCV96ACN4L4N6P6BG6H"
   },
   "criteria":[
      {
         "attribute":"guid",
         "value": [
             "CUEXB8CEPGHGZI18WDMU",
             "M407LIMOZGZQ5TUP27F"
         ],
         "operator":"IS_IN"
      }
   ],
   "criteriaResultsCount": 1,
   "files": [
       {
           "guid": "1P7V0X13DKJWDKJPY982",
           "title": null 
       }
   ],
   "guid":"Z8SPLFQS3K0DTYB56MW",
   "number":12,
   "status":"COMPLETE"
}
```
The request is validated to make sure it doesn’t violate any business rules. Any violation will result in an error response:

* A field is not creatable. 

```

{  
   "status":400,
   "errors":[  
      {  
         "code":4004,
         "message":"The attribute \"name1\" is not creatable."
      }
   ]
}
```
* A value in the export definition is invalid.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The specified value \"Changes\" is not a valid option for the attribute \"world\"."
      }
   ]
}
```
* A required field is missing.

```

{  
   "status":400,
   "errors":[  
      {  
         "code":3006,
         "message":"The attribute \"Description\" is required."
      }
   ]
}
```
