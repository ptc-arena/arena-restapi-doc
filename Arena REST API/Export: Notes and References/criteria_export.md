# Export Criteria
Export Criteria determine which Items are included in an API Export. Through creating criteria, users can create complex searches similar to Advanced Search. 

The simplest form of a criteria is a criterion. A criterion consists of an Arena attribute , a value associated with an attribute, and an operator that links the attribute to the value.

NOTES:
          
          
          
          
        

* Export Definitions cannot be edited or deleted.

* Criteria can be specified in the Export Definition or in the Export Run. 

* Criteria cannot be specified in both the Export Definition and in the Export Run. It also cannot be specified in neither.

* See Criteria: Attribute and Operators for list of supported attributes and operators.

## Criterion Definitions

| Name<br> | Description<br> |
|  --- |  --- | 
| Attribute<br> | An Arena attribute<br> |
| Value<br> | An Arena attribute value associated with an attribute<br> |
| Operator<br> | A comparison of the attribute to a value<br> |
| Criterion<br> | An object containing one attribute, one operator, and one value.<br> |
| Criterion Logic<br> | Boolean logic combining Criterion such as "OR" and "AND"<br> |
| Criterion Group<br> | A collection of one or more criterions separted by criterion logic<br> |
| Criterion Group Logic<br> | Boolean logic combining Criterion Groups<br> |
| Criteria<br> | A collection of one or more criterion groups separated by criterion group logic<br> |

## Criteria Examples
* A Criterion

```
   "criteria":[
      {
         "attribute":"number",
         "operator":"IS_EQUAL_TO",
         "value":"20-0001"
      }
   ]
```
* Two Criterion separated with criterion logic

```
   "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"20-"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_AFTER",
           "value":"2020-03-02T12:01:07Z"
         }
      ]
}
```
* Three criterions seprated with criterion logic.

```
  "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"1"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_EQUAL_TO",
           "value":"2020-03-02T12:01:07Z"
         },
         "OR",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_BEFORE",
           "value": "2016-01-01T12:00:00Z"
         }
      ]
}
```
* Two Criterion groups separated by criterion gorup logic.

```
   "criteria":[
      [
         {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"9"
         },
         "AND",
         {
           "attribute":"effectiveDateTime",
           "operator":"IS_BEFORE",
           "value":"2019-04-01T12:00:00Z"
         }
      ],
      "OR",
     [  
        {
           "attribute":"number",
           "operator":"STARTS_WITH",
           "value":"7"
        },
        "AND",
        {
           "attribute":"effectiveDateTime",
           "operator":"IS_AFTER"
           "value":"2019-04-01T12:00:00Z"
        }
     ]
}
```
