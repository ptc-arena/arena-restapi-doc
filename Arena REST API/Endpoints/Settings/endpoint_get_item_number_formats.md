# GET Item Number Formats
/settings/items/numberformats

/settings/items/numberformats/&lt;GUID&gt;

This returns  Compact Item Number Formats. Appending a GUID to the URL returns an Item Number Format \(including all fields\) with that GUID. 

Number formats in Arena are constructed as multiple fields of the following types:
          
          
          
          
        

* Free Text (a specified number of characters)

* Delimiter (a character that acts as a separator)

* Pre-Defined Code List (a drop-down list that the user can pick from when creating a new Item Number. In the API, it is called VALUE_LIST)

* Auto-Generated Sequence (an incrementing number)


For more on Item Numbers in Arena, see Arena Help or download the Arena User Manual.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in the response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get all item number formats

GET /settings/items/numberformats

```
{
   "count":6,
   "results":[
      {
         "creationDateTime":"2011-02-05T00:08:14Z",
         "default":false,
         "exampleNumber":"150-0001",
         "guid":"VDXGZ7GGDUDM5O7OL7R3",
         "name":"Assembly"
      },
      {
         "creationDateTime":"2011-01-05T00:26:30Z",
         "default":false,
         "exampleNumber":null,
         "guid":"WEYH08HHEVEN6P8PM8SK",
         "name":"Basic Item Number"
      },
      {
         "creationDateTime":"2015-06-25T18:32:14Z",
         "default":false,
         "exampleNumber":"084-0071-0001",
         "guid":"FXH0JR00XEX6P8R839NG",
         "name":"Discrete Components"
      },
      {
         "creationDateTime":"2011-02-05T00:03:24Z",
         "default":false,
         "exampleNumber":"070-0001",
         "guid":"YG0J2AJJGXGP8RAROAUE",
         "name":"Electrical"
      },
      {
         "creationDateTime":"2011-02-05T00:22:21Z",
         "default":false,
         "exampleNumber":"060-0001",
         "guid":"ZH1K3BKKHYHQ9SBSPBVT",
         "name":"Labels and Packaging"
      },
      {
         "creationDateTime":"2011-02-05T00:13:34Z",
         "default":false,
         "exampleNumber":"081-0001",
         "guid":"0I2L4CLLIZIRATCTQCWD",
         "name":"Mechanical"
      }
   ]
}
```
Get an item number format with a specific GUID

/settings/items/numberformats/YG0J2AJJGXGP8RAROAUE

```
{
   "creationDateTime":"2011-02-05T00:03:24Z",
   "default":false,
   "exampleNumber":"070-0001",
   "fields":[
      {
         "apiName":"6O8RAIRRO5M9SBUBJWGL",
         "guid":"6O8RAIRRO5M9SBUBJWGL",
         "maxLength":null,
         "name":"Component Type",
         "possibleValues":[
            {
               "description":"Capacitor",
               "value":"070"
            },
            {
               "description":"Resistor",
               "value":"071"
            },
            {
               "description":"Connector",
               "value":"072"
            },
            {
               "description":"Crystal",
               "value":"073"
            },
            {
               "description":"Integrated Circuit",
               "value":"074"
            },
            ...
         ],
         "type":"VALUE_LIST",
         "value":null
      },
      {
         "apiName":"BTDWFNWWTAREXGZGO0JH",
         "guid":"BTDWFNWWTAREXGZGO0JH",
         "maxLength":null,
         "name":null,
         "possibleValues":[

         ],
         "type":"DELIMITER",
         "value":"-"
      },
      {
         "apiName":"CUEXGOXXUBSFYH0HP1KR",
         "guid":"CUEXGOXXUBSFYH0HP1KR",
         "maxLength":null,
         "name":"Sequence",
         "possibleValues":[

         ],
         "type":"AUTO_SEQUENCE",
         "value":null
      }
   ],
   "guid":"YG0J2AJJGXGP8RAROAUE",
   "name":"Electrical"
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
