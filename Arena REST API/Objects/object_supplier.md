# Supplier

| Field<br> | Data Type<br> | Description<br> |
|  --- |  --- |  --- | 
| accountNumber<br> | Integer<br> | The account number of the supplier<br> |
| additionalAttributes<br> | Array of Attributes<br> | The additional attributes of an item. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute.<br> |
| addresses<br> | Array of addresses<br> | The addresses associated with a supplier. Each address entry includes address1, address2, city, Country/Region, label, postalCode, province, and state. Each address also includes the primary attribute, which indicates whether or not an address is the primary one for this supplier. For permissible values for Country/Region and state, see the Create New Supplier workflow in the Arena application.<br> |
| approvalStatus<br> | Boolean<br> | Indicates whether or not a supplier is listed as approved. This value can be approved or disapproved.<br> |
| creationDateTime<br> | Date-Formatted String<br> | the date and time \(in Zulu format\) a supplier was created.<br> |
| creator<br> | Reference<br> | The creator of the supplier record. Contains the full name of the creator.<br> |
| description<br> | String<br> | The description of a supplier<br> |
| guid<br> | String<br> | The unique identifier of a supplier<br> |
| name<br> | String<br> | The name of a supplier<br> |
| phoneNumbers<br> | Array of phone numbers<br> | The phone numbers associated with a supplier. Each entry includes comment, extension, label, and number.<br> |
| supplierId<br> | String<br> | The unique identifier of a supplier in the Arena database<br> |
| website<br> | String<br> | The website of a supplier<br> |

