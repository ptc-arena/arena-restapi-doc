# Import Options (Item Specs and Item BOM)
The table below lists import options \(for Item Specs and Item BOM imports\) with the modes they are supported. Supported values \(when applicable\) are listed in capitol letters. Empty cells indicate that the import option is not supported within that mode.


| Import Option | Create | Edit | Overwrite | Replace | Delete |
|  --- |  --- |  --- |  --- |  --- |  --- | 
| createDuplicates | 
              
             |   |   |   |   |
| matchDuplicates |   | 
              
             | 
              
             |   | 
              
             |
| matchDuplicateParents |   |   |   | 
              
             |   |
| removeValue |   | When editing attributes, an empty value in the source file typically indicates that the value should not change. In order to change the value to be empty, the string represented by the option “removeValue” can be used. When this value appears in the source file, values entered in that attribute will be removed. The default value for “removeValue” is “\[Remove Value\]”. If the attribute is required, then an error shall be returned, and the default value shall not be used. | When editing attributes, an empty value in the source file typically indicates that the value should not change. In order to change the value to be empty, the string represented by the option “removeValue” can be used. When this value appears in the source file, values entered in that attribute will be removed. The default value for “removeValue” is “\[Remove Value\]”. If the attribute is required, then an error shall be returned, and the default value shall not be used. |   |   |
| multiSelectDelimiter  |  Multiselect lists are submitted with multiple values in a text field. The values are delimited with the value in option “multiSelectDelimiter”. The default value is a semicolon \(\;\) if not specified. | Multiselect lists are submitted with multiple values in a text field. The values are delimited with the value in option “multiSelectDelimiter”. The default value is a semicolon \(\;\) if not specified. | Multiselect lists are submitted with multiple values in a text field. The values are delimited with the value in option “multiSelectDelimiter”. The default value is a semicolon \(\;\) if not specified. | Multiselect lists are submitted with multiple values in a text field. The values are delimited with the value in option “multiSelectDelimiter”. The default value is a semicolon \(\;\) if not specified. |   |
| checkRefDes | 
              
             | 
              
             | 
              
             | 
              
             |   |
| timeZone | DateTime values must be specified using ISO\-8601 which must include time and optionally time zone. If time zone information is not included, the option “timeZone” can be specified for the import to set the time zone accordingly. Since the default is UTC, timeZone should be specified for date attributes that are not within the United Kingdom. | DateTime values must be specified using ISO\-8601 which must include time and optionally time zone. If time zone information is not included, the option “timeZone” can be specified for the import to set the time zone accordingly. Since the default is UTC, timeZone should be specified for date attributes that are not within the United Kingdom | DateTime values must be specified using ISO\-8601 which must include time and optionally time zone. If time zone information is not included, the option “timeZone” can be specified for the import to set the time zone accordingly. Since the default is UTC, timeZone should be specified for date attributes that are not within the United Kingdom | DateTime values must be specified using ISO\-8601 which must include time and optionally time zone. If time zone information is not included, the option “timeZone” can be specified for the import to set the time zone accordingly. Since the default is UTC, timeZone should be specified for date attributes that are not within the United Kingdom |   |
| addToChange | Adds imported items to a change. Supported values: | Adds imported items to a change. Supported values: | Adds imported items to a change. Supported values: | Adds imported items to a change. Supported values: |   |
| stripWhiteSpace | 
              
             | 
              
             | 
              
             | 
              
             | 
              
             |
| numberingFreeTextHeader | A single Free Text field shall be supported for item numbers using a numbering sequence. The free text content shall be taken from a dedicated column in the import source file. The column header shall be named as specified in the option "numberingFreeTextHeader". This shall default to "Numbering Free Text" if not supplied. When an item number is generated using item numbering and the item numbering has a single Free Text field: | A single Free Text field shall be supported for item numbers using a numbering sequence. The free text content shall be taken from a dedicated column in the import source file. The column header shall be named as specified in the option "numberingFreeTextHeader". This shall default to "Numbering Free Text" if not supplied. When an item number is generated using item numbering and the item numbering has a single Free Text field: | A single Free Text field shall be supported for item numbers using a numbering sequence. The free text content shall be taken from a dedicated column in the import source file. The column header shall be named as specified in the option "numberingFreeTextHeader". This shall default to "Numbering Free Text" if not supplied. When an item number is generated using item numbering and the item numbering has a single Free Text field: |   |   |

* ALLOW permits duplicates to be created if permitted by settings. 

* ERROR returns an error indicating that there are duplicate resources are permitted by Arena. Default value if not specified.

* APPLY_TO_ALL applies the edit to all resources matching the key attributes

* ERROR returns an error indicating that there are duplicates \(default if not specified\)

* APPLY_TO_ALL applies the edit to all resources matching the key attributes

* ERROR returns an error indicating that there are duplicates \(default if not specified\)

* APPLY_TO_ALL applies the delete to all resources matching the key attributes.

* ERROR returns an error indicating there are duplicates.

* ALLOW replaces view resources for all matching parent resources.

* ERROR returns an error indicating that there are duplicate parent resources. \(Default\).

* CHECK runs a check on the reference designators for every created and edited BOM Line. \(Default\).

* DO_NOT_CHECK value prevents a reference designator check.

* CHECK runs a check on the reference designators for every created and edited BOM Line. \(Default\).

* DO_NOT_CHECK value prevents a reference designator check.

* CHECK runs a check on the reference designators for every created and edited BOM Line. \(Default\).

* DO_NOT_CHECK value prevents a reference designator check.

* CHECK runs a check on the reference designators for every created and edited BOM Line. \(Default\).

* DO_NOT_CHECK value prevents a reference designator check

* An existing and valid change GUID

* An existing and valid change number.

* A valid POST CHANGES request body.

* An existing and valid change GUID

* An existing and valid change number

* A valid POST CHANGES request body

* An existing and valid change GUID

* An existing and valid change number

* A valid POST CHANGES request body

* An existing and valid change GUID

* An existing and valid change number

* A valid POST CHANGES request body

* STRIP strips white space from the source for all atrributes. Default.

* RETAIN does not strip white space from the source file.

* STRIP strips white space from the source for all atrributes. Default.

* RETAIN does not strip white space from the source file

* STRIP strips white space from the source for all atrributes. Default

* RETAIN does not strip white space from the source file

* STRIP strips white space from the source for all atrributes. Default

* RETAIN does not strip white space from the source file

* STRIP strips white space from the source for all atrributes. Default

* RETAIN does not strip white space from the source file

* If the numberingFreeTextHeader column is supplied, and there is a value for the item, this value shall be used in the free text.

* 
If the numberingFreeTextHeader column is supplied, and there is NO value for the item, the default value for the free text field shall be used. If there is not default value, then there shall be an error.

* If the numberingFreeTextHeader column is not supplied, then the default value for the free text field shall be used. If there is not default value, then there shall be an error.

* If the numberingFreeTextHeader column is supplied, and there is a value for the item, this value shall be used in the free text.

* 
If the numberingFreeTextHeader column is supplied, and there is NO value for the item, the default value for the free text field shall be used. If there is not default value, then there shall be an error.

* If the numberingFreeTextHeader column is not supplied, then the default value for the free text field shall be used. If there is not default value, then there shall be an error.

* If the numberingFreeTextHeader column is supplied, and there is a value for the item, this value shall be used in the free text.

* 
If the numberingFreeTextHeader column is supplied, and there is NO value for the item, the default value for the free text field shall be used. If there is not default value, then there shall be an error.

* If the numberingFreeTextHeader column is not supplied, then the default value for the free text field shall be used. If there is not default value, then there shall be an error.

