# GET Items (Search) Criteria Parameter


/items?criteria=&lt;URL encoded criteria&gt;

This article describes a special variation of the  endpoint that uses the criteria search parameter.

Using the Criteria parameter requires URL encoding of the query string. URL encoding, also known as Percent\-encoding, encodes data in using only the limited US\-ASCII characters. Typically special characters are encoded with percentages and numbers.

The Criteria search parameter utilizes the same attributes and operators used in API Item Export. See  for a full list of attributes and operators that can be used for the Criteria parameter.

Additional information on criteria structure is available in .



## Criteria Parameter Search Examples
Get all items with a creation date between 2001\-07\-12T10:00:01Z and 2030\-07\-12T20:23:59Z.

Below is the non url encoded version. This should not be used but is included here for instructional purposes.



GET /items?criteria=\[\[  \{ "attribute": "creationDateTime", "value": \["2001\-07\-12T10:00:01Z" ,"2030\-07\-12T20:23:59Z" \], "operator": "IS_BETWEEN" \} \] \]

Below is the url encoded criteria parameter search version that should be used.

GET items?criteria=%5B%5B%20%20%7B%20%22attribute%22%3A%20%22creationDateTime%22%2C%20%22value%22%3A%20%5B%222015\-07\-12T10%3A00%3A01Z%22%20%2C%222020\-07\-12T20%3A23%3A59Z%22%20%5D%2C%20%22operator%22%3A%20%22IS_BETWEEN%22%20%7D%20%5D%20%5D

Example Response

```
{
    "count": 16,
    "results": [
        {
            "category": {
                "guid": "ASCVERC3QTCM5O07B6HP"
            },
            "creationDateTime": "2016-09-02T18:48:29Z",
            "effectiveDateTime": "2016-09-02T19:20:10Z",
            "guid": "1J3M5I3UHK3BU9XRO93Q",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Policy, Quality",
            "number": "001-00001",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/1J3M5I3UHK3BU9XRO93Q",
                "app": "https://app.bom.com/1J3M5I3UHK3BU9XRO93Q"
        },
        {
            "category": {
                "guid": "CUEXGTE5SVEO7Q29D8JI"
            },
            "creationDateTime": "2016-09-02T18:49:25Z",
            "effectiveDateTime": "2016-09-02T19:20:10Z",
            "guid": "6O8RAN8ZMP8GZE2WTE76",
            "inAssembly": false,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Everyroad Employee Handbook",
            "number": "010-00001",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/6O8RAN8ZMP8GZE2WTE76",
                "app": "https://app.bom.com/6O8RAN8ZMP8GZE2WTE76"                   },
            ...   
    ]
}
```
Get items with a lifecycle phase guid of 9RBUDQB2PSADWFYH0AUY.

Below is the non url encoded version. This should not be used but is included here for instructional purposes.



GET /items?criteria=\[ \[ \{ "attribute": "lifecyclePhase.guid", "value": \[ "9RBUDQB2PSADWFYH0AUY"\], "operator": "IS_IN" \} \] \]

Below is the url encoded criteria parameter search version that should be used.

GET /items?criteria=%5B%20%5B%20%7B%20%22attribute%22%3A%20%22lifecyclePhase.guid%22%2C%20%22value%22%3A%20%5B%20%229RBUDQB2PSADWFYH0AUY%22%5D%2C%20%22operator%22%3A%20%22IS_IN%22%20%7D%20%5D%20%5D

Example Response

```
{
    "count": 20,
    "results": [
        {
            "assemblyType": "NOT_AN_ASSEMBLY",
            "category": {
                "guid": "J1L4N0LCZ2LVEXCJJK6K"
            },
            "creationDateTime": "2011-06-02T19:23:22Z",
            "effectiveDateTime": "2011-07-19T16:28:45Z",
            "guid": "DVFYHUF6TWFN6OYHTN2A",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Socket, Molex D50-L RA 20pin",
            "number": "125-00006",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/DVFYHUF6TWFN6OYHTN2A",
                "app": "https://app.bom.com/DVFYHUF6TWFN6OYHTN2A"
        },
        {
            "assemblyType": "NOT_AN_ASSEMBLY",
            "category": {
                "guid": "J1L4N0LCZ2LVEXCJJK6K"
            },
            "creationDateTime": "2011-06-02T19:23:25Z",
            "effectiveDateTime": "2011-07-19T16:28:45Z",
            "guid": "I0K3MZKBY1KSBT3MYS65",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Plug, Molex D50-L Straight, 20pin",
            "number": "125-00007",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/I0K3MZKBY1KSBT3MYS65",
                "app": "https://app.bom.com/I0K3MZKBY1KSBT3MYS65"
        },
        {
            "category": {
                "guid": "J1L4N0LCZ2LVEXCJJK6K"
            },
            "creationDateTime": "2011-06-02T19:23:27Z",
            "effectiveDateTime": "2011-07-19T16:28:45Z",
            "guid": "N5P8R4PG36PXGY8R3XAH",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Connector, Molex KK 3 cond straight",
            "number": "125-00008",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/N5P8R4PG36PXGY8R3XAH",
                "app": "https://app.bom.com/N5P8R4PG36PXGY8R3XAH"
        },
        ...
    ]
}       
```
Get Items that have a value equal to WEYH0DYPCFWFYH0JSIPD for creator guid OR were created by a user who has an email that contains the value hwalker@everyroadgps.com.

Below is the non url encoded version. This should not be used but is included here for instructional purposes.



GET /items?criteria=\[ \[ \{ "attribute": "creator.guid", "value": "WEYH0DYPCFWFYH0JSIPD", "operator": "IS_EQUAL_TO" \} \], "OR", \[ \{ "attribute": "creator.email", "value": "hwalker@everyroadgps.com", "operator": "CONTAINS" \} \] \]

Below is the url encoded criteria parameter search version that should be used.

GET /items?criteria=%5B%20%5B%20%7B%20%22attribute%22%3A%20%22creator.guid%22%2C%20%22value%22%3A%20%22WEYH0DYPCFWFYH0JSIPD%22%2C%20%22operator%22%3A%20%22IS_EQUAL_TO%22%20%7D%20%5D%2C%20%22OR%22%2C%20%5B%20%7B%20%22attribute%22%3A%20%22creator.email%22%2C%20%22value%22%3A%20%22hwalker%40everyroadgps.com%22%2C%20%22operator%22%3A%20%22CONTAINS%22%20%7D%20%5D%20%5D

Example Response

```
{
    "count": 20,
    "results": [
        {
            "assemblyType": "NOT_AN_ASSEMBLY",
            "category": {
                "guid": "I0K3MZKBY1KUDWBIIJ49"
            },
            "creationDateTime": "2012-03-07T19:54:07Z",
            "effectiveDateTime": "2012-03-07T19:56:04Z",
            "guid": "2K4N6J4VIL4CVA8EYV18",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "EWGZIVG7UXFI1K3M5FZN",
                "name": "In Design"
            },
            "name": "Voltage Regulator, Low-dropout, 5.0V, 90µA",
            "number": "160-00007",
            "revisionNumber": "1",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/2K4N6J4VIL4CVA8EYV18",
                "app": "https://app.bom.com/2K4N6J4VIL4CVA8EYV18"
        },
        {
            "assemblyType": "NOT_AN_ASSEMBLY",
            "category": {
                "guid": "5N7Q9M7YLO7H0JY556R1"
            },
            "creationDateTime": "2012-04-04T18:25:22Z",
            "guid": "XFZI1EZQDGZ7Q535R6XM",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "9RBUDQB2PSADWFYH0AUY",
                "name": "Unreleased"
            },
            "name": "Resistor, Surface Mount, 240ohm, 1/10W, 0603",
            "number": "180-00013",
            "revisionNumber": "01",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/XFZI1EZQDGZ7Q535R6XM",
                "app": "https://app.bom.com/XFZI1EZQDGZ7Q535R6XM"
        },
        {
            "assemblyType": "TOP_LEVEL_ASSEMBLY",
            "category": {
                "guid": "WEYH0DYPCFY8RAPWWXIF"
            },
            "creationDateTime": "2011-08-09T22:19:25Z",
            "effectiveDateTime": "2013-03-13T18:58:37Z",
            "guid": "3L5O7K5WJM5DWB91YGJ7",
            "inAssembly": false,
            "lifecyclePhase": {
                "guid": "EWGZIVG7UXFI1K3M5FZN",
                "name": "In Design"
            },
            "name": "PCBA, EveryRoad, Model 500",
            "number": "830-00002",
            "revisionNumber": "3",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/3L5O7K5WJM5DWB91YGJ7",
                "app": "https://app.bom.com/3L5O7K5WJM5DWB91YGJ7"
        },
        ...
    ]
}
```
Search for Items that have a Category GUID value of CUEXGTE5SVEO7Q29D8JI or a Category GUID value of  BTDWFSD4RUDN6P18C7I6. OR a Category GUID value of J1L4N0LCZ2LVEX9H2599 or a Lifecycle Phase GUID value of BTDWFSD4RUCFYH0J2CWA. Or a Lifecycle Phase GUID of ASCVERC3QTBEXGZI1BVF or an Item number that starts with a value of 8.

Below is the non url encoded version. This should not be used but is included here for instructional purposes.

GET /items?criteria=\[ \[ \{"attribute": "category.guid","value": "CUEXGTE5SVEO7Q29D8JI","operator": "IS_EQUAL_TO"\},"OR",\{"attribute": "category.guid","value": "BTDWFSD4RUDN6P18C7I6","operator": "IS_EQUAL_TO"\} \],  "OR", \[\{"attribute": "category.guid","value": "J1L4N0LCZ2LVEX9H2599","operator": "IS_EQUAL_TO"\}\], "OR", \[\{"attribute": "lifecyclePhase.guid","value": "BTDWFSD4RUCFYH0J2CWA","operator": "IS_EQUAL_TO"\}\], "OR", \[ \{"attribute": "lifecyclePhase.guid","value": "ASCVERC3QTBEXGZI1BVF","operator": "IS_EQUAL_TO"\},"OR",\{"attribute": "number","value": "8","operator": "STARTS_WITH"\} \] \]

Below is the url encoded criteria parameter search version that should be used.

GET /items?criteria=%5B%20%5B%20%7B%22attribute%22%3A%20%22category.guid%22%2C%22value%22%3A%20%22CUEXGTE5SVEO7Q29D8JI%22%2C%22operator%22%3A%20%22IS_EQUAL_TO%22%7D%2C%22OR%22%2C%7B%22attribute%22%3A%20%22category.guid%22%2C%22value%22%3A%20%22BTDWFSD4RUDN6P18C7I6%22%2C%22operator%22%3A%20%22IS_EQUAL_TO%22%7D%20%5D%2C%20%20%22OR%22%2C%20%5B%7B%22attribute%22%3A%20%22category.guid%22%2C%22value%22%3A%20%22J1L4N0LCZ2LVEX9H2599%22%2C%22operator%22%3A%20%22IS_EQUAL_TO%22%7D%5D%2C%20%22OR%22%2C%20%5B%7B%22attribute%22%3A%20%22lifecyclePhase.guid%22%2C%22value%22%3A%20%22BTDWFSD4RUCFYH0J2CWA%22%2C%22operator%22%3A%20%22IS_EQUAL_TO%22%7D%5D%2C%20%22OR%22%2C%20%5B%20%7B%22attribute%22%3A%20%22lifecyclePhase.guid%22%2C%22value%22%3A%20%22ASCVERC3QTBEXGZI1BVF%22%2C%22operator%22%3A%20%22IS_EQUAL_TO%22%7D%2C%22OR%22%2C%7B%22attribute%22%3A%20%22number%22%2C%22value%22%3A%20%228%22%2C%22operator%22%3A%20%22STARTS_WITH%22%7D%20%5D%20%5D

Example Response

```
{
    "count": 20,
    "results": [
        {
            "assemblyType": "ASSEMBLY",
            "category": {
                "guid": "VDXGZCXOBEX7Q9OVVWHR"
            },
            "creationDateTime": "2011-06-02T19:23:30Z",
            "effectiveDateTime": "2011-07-26T06:54:20Z",
            "guid": "HZJ2LYJAX0JRAS1RLQS5",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Documentation Package, Everyroad Model 300/500",
            "number": "820-00003",
            "revisionNumber": "A",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/HZJ2LYJAX0JRAS1RLQS5",
                "app": "https://app.bom.com/HZJ2LYJAX0JRAS1RLQS5"
        },
        {
            "assemblyType": "ASSEMBLY",
            "category": {
                "guid": "VDXGZCXOBEX7Q9OVVWHR"
            },
            "creationDateTime": "2011-06-02T19:23:31Z",
            "effectiveDateTime": "2012-01-12T23:55:37Z",
            "guid": "BTDWFSD4RUDL4MK9ZROI",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Subassembly, EveryRoad, Front Assembly",
            "number": "820-00001",
            "revisionNumber": "C",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/BTDWFSD4RUDL4MK9ZROI",
                "app": "https://app.bom.com/BTDWFSD4RUDL4MK9ZROI"
        },
        {
            "assemblyType": "ASSEMBLY",
            "category": {
                "guid": "VDXGZCXOBEX7Q9OVVWHR"
            },
            "creationDateTime": "2011-06-02T19:23:31Z",
            "effectiveDateTime": "2012-01-12T23:55:37Z",
            "guid": "M4O7Q3OF25OWFWL0UWAS",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Subassembly, EveryRoad, Rear Assembly",
            "number": "820-00002",
            "revisionNumber": "F",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/M4O7Q3OF25OWFWL0UWAS",
                "app": "https://app.bom.com/M4O7Q3OF25OWFWL0UWAS"
        },
        {
            "assemblyType": "ASSEMBLY",
            "category": {
                "guid": "FXH0JWH8VYHRAT8FFG2G"
            },
            "creationDateTime": "2011-06-02T19:23:30Z",
            "effectiveDateTime": "2015-09-21T23:45:20Z",
            "guid": "7P9SBO90NQ9H0H64Z4M0",
            "inAssembly": true,
            "lifecyclePhase": {
                "guid": "DVFYHUF6TWEH0J2L4EYV",
                "name": "In Production"
            },
            "name": "Assembly, GPS, EveryRoad Car Navigation Unit - Model 300",
            "number": "810-00001",
            "revisionNumber": "E",
            "url": {
                "api": "https://api.arenasolutions.com/v1/items/7P9SBO90NQ9H0H64Z4M0",
                "app": "https://app.bom.com/7P9SBO90NQ9H0H64Z4M0"
        },
        ...
    ]
}
```
