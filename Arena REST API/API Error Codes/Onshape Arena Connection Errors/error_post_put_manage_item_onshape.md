# Errors When Updating and Creating Items
Item management includes Item creation and updates that apply core and custom attributes. This process starts when an Onshape part is synced with Arena. If the Onshape part is new and assigned a reserved number then a POST /items endpoint will create the item in Arena. If the Onshape part exists in Arena then a PUT /items endpoint updates the Arena item.

POST /items

PUT /items

These endpoints are used to create or update items with basic & attributes. The POST /login & POST /login/authorizeuser endpoints are a pre\-requisite prior to it’s execution.    The Onshape User Arena authorize user must have a Full License, Item Read & Write and File Read & Edit Access Policy Rules in Arena. If the POST /items endpoint fails then the part should not be created. If the PUT /items endpoint fails then that specific update will not be applied. However, if the previous PUT /items were successful then those updates will be applied. 


| Status Code | Error Code | Message | Explanation |
|  --- |  --- |  --- |  --- | 
| 400 | 3001 |   |   |
| 400 | 3215 |   | The Core Attribute \(i.e. Description, Name, Revision, etc\) is required and is being assigned a blank value. Replace blank with an acceptable value an re\-run the process. |
| 400 | 3103 |   | The Core Attribute \(i.e. Description, Name, Revision,…,etc\) is being assigned text that exceeds the text length limit. Shorten the values and re\-runthe process. |
| 400 | 3105 |   |  The Core Attribute \(i.e. Description, Name\) has been setup to not include lowercase characters. |
| 400 | 3106 |   | The Core Attribute \(i.e. Description, Name\) has been setup to not include uppercase characters. Convert uppercase to lowercase and re\-run the process. |
| 400 | 3107 |   | The Core Attribute \(i.e. Description, Name\) has been setup to not include numeric characters. Remove numerics and re\-run process. |
| 400 | 3108 |   | The Core Attribute has been setup to not include specific text. Remove the excluded text and re\-run the process. |
| 400 | 4003 |   | The Core Attribute Procurement Type must be assigned “OTS” or “MTS” in Arena. Assign an acceptable value and re\-run the process.  |
| 400 | 2008 |   | The Additional Attribute is required and is being omitted.  |
| 400 | 2014 |   | The Additional Attribute is required and is being assigned an empty value. Assign an acceptable value and re\-run the process. |
| 400 | 2002 |   |  The Additional Attribute is Predefined Drop List that is being assigned a value that does not exist in the list of values. Assign an acceptable value and re\-run the process. |
| 400 | 2021 |   | The Additional Attribute is Predefined Drop List that is being assigned a value that does not exist in the list of values. Assign an acceptable value and re\-run the process. |
| 400 | 2003 |   | The Additional Attribute is Date Type file that is being assigned a non\-Date value or a date value format that is not compatible with what Arena accepts. Update date and re\-run the process. |
| 400 | 2022 |   | The Additional Attribute is Date Type file that is being assigned a non\-Date value. Update date and re\-run the process. |
| 400 | 2004 |   | The Additional Numeric Attribute is being assigned a Non\-Numeric value. |
| 400 | 2005 |   | The Additional Numeric Attribute is being assigned a Negative Numeric value. |
| 400 | 2023 |   | The Additional Numeric Attribute is being assigned a Negative Numeric value. |
| 400 | 2007 |   | The Additional Multi Select Attribute is being assigned more values than is allowed. |
| 400 | 2025 |   | The Additional Attribute is Multi\-Select Predefined Drop List that is being assigned more values that is allowed.  |
| 400 | 2006 |   | The Additional Attribute is Numeric Type that is limited to a specific number of decimal places. |
| 400 | 2024 |   | The Additional Attribute is Numeric Type that is limited to a specific number of decimal places. |
| 400 | 2010 |   | The Additional Attribute is Multi\-Select Predefined Drop List that is being assigned an invalid value. Assign an acceptable value and re\-run the process. |
| 400 | 2026 |   | The Additional Attribute is Multi\-Select Predefined Drop List that is being assigned more multiple values that is allowed. Assign an acceptable value and re\-run the process. |
| 400 | 2029 |   | The Additional Attribute is Numeric Type that does not allow non\-numeric values. |

```
The attribute “{0}” is required.
```
The Core Attribute \(i.e. Description, Name, Revision, etc\) is required and is being omitted.  Acceptable values must be assigned prior to re\-running the process again:

Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items \- See what is required.

Example: The attribute “\name\”” is required.

\{0\} \- Arena Item Core Attribute.

```
Empty or blank is not a valid option for the attribute “{0}”.
```
Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items \- See what is required.

Example: Empty or blank is not a valid option for the attribute “\description\”.

\{0\} \- Arena Item Core Attribute.

```
The length of the value exceeds the maximum length “{0}” for the attribute “{1}”.
```
Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items \- See  the text length limit.

Example: The length of the value exceeds the maximum length \(10\) for the attribute \"name\".

\{0\} \- Arena Item Core Attribute Maximum Length.

\{1\} \- Arena Item Core Attribute.

```
The value for attribute "{0}" cannot include lowercase characters.
```
Convert lowercase to uppercase and re\-run the process.

Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items 

Example: The value for attribute \"name\" cannot include lowercase  characters.

\{0\} \- Arena Item Core Attribute.

```
The value for attribute "{0}" cannot include uppercase characters.
```
Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items 

Example: The value for attribute \"name\" cannot include uppercase  characters.

\{0\} \- Arena Item Core Attribute.

```
The value for attribute "{0}" cannot include numeric characters.
```
Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items.

Example: The value for attribute "\description\" cannot include numeric characters.

\{0\} \- Arena Item Core Attribute.

```
The value for attribute "{0}" cannot include "{1}".
```
Arena Administrator:  Check Workspace Settings &gt; Attributes &gt; Items.

Example: The value for attribute "\name\" cannot include "TBD".

\{0\} \- Arena Item Core Attribute.

\{1\} \- Invalid Text.

```
The value for the attribute “{0}” is not valid.
```
Example: The value for the attribute \"procurementType\" is not valid.

\{0\} \- Arena Item Core Attribute Procurement Type.

```
The additional attribute ”{0}””{1}” is required.
```
Onshape: Property Not Mapped to Arena Additional Attribute. The property may need to be mapped to an Arena Item Attribute.

Arena Administrator: Check Workspace Settings &gt; Attributes &gt; Items & Settings &gt; Categories &gt; Items \- See what is required.

Example: The additional attribute \"Critical Part\" \(guid 0I2LQFJ66IZH0JY1VR5G\) is required.

\{0\} \- Arena Item Core Attribute.

\{1\} \- Arena Item Core Attribute GUID.

```
Empty or blank is not a valid option for the additional attribute “{0}””{1}”.
```
Onshape: Property Mapped to Arena Additional Attribute but value is not assigned. 

Arena: Check Workspace Settings &gt; Attributes &gt; Items & Settings &gt; Categories &gt; Items \- See what is required.

Example: Empty or blank is not a valid option for additional attribute \"Critical Part\" \(guid 0I2LQFJ66IZH0JY1VR5G\).

\{0\} \- Arena Item Core Attribute.

\{1\} \- Arena Item Core Attribute GUID.

```
The specified value "{0}" is not a valid option for additional attribute "{1}".
```
Onshape: Property Mapped to Arena Additional Attribute but value list does not match the Arena Attribute value list. Compare the lists between Onshape and Arena.

Example: The specified value \"X\" is not a valid option for additional attribute \"RoHS Compliant\".

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

```
The specified value "{0}" is not a valid option for additional attribute "{1}" (guid {2}).
```
Onshape: Property Mapped to Arena Additional Attribute but value list does not match the Arena Attribute value list.Compare the lists between Onshape and Arena.

Example: The specified value \"X\" is not a valid option for additional attribute \"RoHS Compliant\" \(guid GUID\).

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID

```
The value "{0}" is not valid for additional attribute "{1}" of Date type.
```
Onshape: Property Mapped to Arena Additional Attribute but value assigned does not meet the Arena Attribute Date Value or Format requirements.

Example: The value \"X\" is not valid for additional attribute \"ADate\" of Date type.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

```
The value "{0}" is not valid for additional attribute "{1}" (guid {2}) of Date type.
```
Onshape: Property Mapped to Arena Additional Attribute but value assigned does not meet the Arena Attribute Date Value or Format requirements.

Example: The value \"X\" is not valid for additional attribute \"ADate\" \(guid GUID\) of Date type.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

```
The value "{0}" is not valid for additional attribute "{1}" of Number type.
```
Onshape: Property Mapped to Arena Additional Attribute but value assigned does not meet the Arena Attribute Number Value or Format requirements. Compare the Onshape Property & Arena Item Attribute Type.

Example: The value \"\-1\" for additional attribute \"POS Number 1\" must be positive.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

```
The value "{0}" for additional attribute "{1}" must be positive.
```
Onshape: Property Mapped to Arena Additional Attribute that does not allow negative numbers. Change the value to positive. Check the Arena Item Attribute Requirements.

Example: The value \"\-1\" for additional attribute \"POS Number 1\" must be positive.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

```
The value "{0}" for additional attribute "{1}" (guid {2}) must be positive.
```
Onshape: Property Mapped to Arena Additional Attribute that does not allow negative numbers. Change the value to positive. Check the Arena Item Attribute Requirements.

Example: The value \"\-1\" for additional attribute \"POS Number 1\" \(guid GUID\) must be positive.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

```
The number of values for additional attribute "{1}" must not exceed "{0}".
```
Onshape: Property Mapped to an Arena Additional Attribute Multi\-Select Predefined Drop List that is being assigned more values that is allowed. Reduce the number of values to select and re\-run the process.

Example: The number of values for additional attribute \"ABCs\" must not exceed \"2\".

\{0\} \- Number of Onshape Values Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

```
The number of values for additional attribute "{1}" (guid {2}) must not exceed "{0}".
```
Onshape: Property Mapped to an Arena Additional Attribute Multi\-Select Predefined Drop List that is being assigned more values that is allowed. Reduce the number of values to select and re\-run the process.

Example: The number of values for additional attribute \"ABCs\" \(guid GUID\) must not exceed \"2\".

\{0\} \- Number of Onshape Values Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

```
The value "{0}" for additional attribute "{1}" allows "{2}" decimal places.
```
Onshape: Property Mapped to Arena Additional Attribute that only requires a specific number of decimal places that is not being met by Onshape. Update the number and re\-run the process. 

Example: The value \"1.22\" for additional attribute \"POS Number 1\" allows \"0\" decimal places.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Numeric Attribute Decimal Places.

```
The value "{0}" for additional attribute "{1}" (guid {2}) allows "{3}" decimal places.
```
Onshape: Property Mapped to Arena Additional Attribute that only requires a specific number of decimal places that is not being met by Onshape. Update the number and re\-run the process.

Example: The value \"1.22\" for additional attribute \"POS Number 1\" \(guid GUID\) allows \"0\" decimal places.

\{0\} \- Onshape Value Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

\{3\} \- Arena Item Additional Numeric Attribute Decimal Places.

```
The specified value "{0}" is not a valid option for multi additional attribute "{1}".
```
Onshape: Property Mapped to Arena Additional Attribute where the value lists don’t match. Compare the Onshape value list and the Arena value list. 

Example: The specified value \"x\" is not a valid option for multi additional attribute \"ABCs\".

\{0\} \- Onshape Values that does not match the Arena Item Additional Attribute Value in the Multi\-Select Drop List.

\{1\} \- Arena Item Additional Attribute Name.

```
The specified value "{0}" is not a valid option for multi additional attribute "{1}" (guid {2}).
```
Onshape: Property Mapped to Arena Additional Attribute but value list contains more values than is allowed in Arena.Compare the Onshape value list and the Arena value list. 

Example: "The specified value \"x\" is not a valid option for multi additional attribute \"ABCs\". \(guid GUID\) "

\{0\} \- Number of Onshape Values Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

```
The value "{0}" is not valid for additional attribute "{1}" (guid {2}) of Number type.
```
Onshape: Property Mapped to Arena Additional Attribute that only requires a positive number that is not being met by Onshape. Update the number and re\-run the process. 

Example: The value \"TBD\" is not valid for additional attribute \"Lead Time Days\" \(guid 3L5OTIM99L2K3M14YU8A\) of Number type.

\{0\} \- Number of Onshape Values Being Assigned.

\{1\} \- Arena Item Additional Attribute Name.

\{2\} \- Arena Item Additional Attribute GUID.

