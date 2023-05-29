# Responses
For calls that return responses \(and not arbitrary binary data\), responses will look roughly like:



```
{
    "<object_field>":"<field_value>"
    …
}

```
When the request returns multiple objects, responses look generally like:



```
{
    "count": 20,
    "results": [
        {
            "<object_field>":"<field_value>"
        },
        …
    ]
}
```
When a request returns  one or more errors:

```
{
    "errors": [
        {
            "code": <error_code>,
            "message": "<error_message>"
        }
    ],
    "status": <error_class>
}
```
To make responses more human\-readable, the first level shows all attributes—attributes with no value will show a default empty value \(e.g., "null", 0\). Second\-level objects are shown in a compact version. In the Get Item response example shown below, the second\-level object "category" includes only the attribute "guid". \(The exception to this rule is the File object, which includes the full version when shown in the second level of a fileAssocation GET.\)

```
{
    "additionalAttributes": [],
    "category": {
        "guid": "5N6P8RAK3MY6UNTA"
    },
    "creationDateTime": "2011-08-09T22:19:25Z",
    "creator": {
        "fullName": "Heidi Walker"
    },
    "description": "Board Assembly...",
    "guid": "0I2LQGHHQXGXGVRR5XND",
    "isAssembly": true,
    "lifecyclePhase": {
        "name": "In Design"
    },
    "name": "PCBA, EveryRoad, Model 500",
    "number": "830-00002",
    "offTheShelf": false,
    "owner": {
        "fullName": "Toshiro Makamuri"
    },
    "productionCost": 108.578,
    "prototypeCost": null,
    "revisionNumber": "3",
    "shared": true,
    "standardCost": 38.505,
    "uom": "each"
}

```
