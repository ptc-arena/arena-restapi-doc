# Supplier

| Field  | Data Type  | Description  |
|  --- |  --- |  --- | 
| accountNumber  | Integer  | The account number of the supplier  |
| additionalAttributes  | Array of Attributes  | The additional attributes of an item. This is an array of additional attributes. Each additional attribute entry includes a value and apiName. The apiName is used to identify this additional attribute.  |
| addresses  | Array of addresses  | The addresses associated with a supplier. Each address entry includes address1, address2, city, Country/Region, label, postalCode, province, and state. Each address also includes the primary attribute, which indicates whether or not an address is the primary one for this supplier. For permissible values for Country/Region and state, see the Create New Supplier workflow in the Arena application.  |
| approvalStatus  | Boolean  | Indicates whether or not a supplier is listed as approved. This value can be approved or disapproved.  |
| creationDateTime  | Date-Formatted String  | the date and time \(in Zulu format\) a supplier was created.  |
| creator  | Reference  | The creator of the supplier record. Contains the full name of the creator.  |
| description  | String  | The description of a supplier  |
| guid  | String  | The unique identifier of a supplier  |
| name  | String  | The name of a supplier  |
| phoneNumbers  | Array of phone numbers  | The phone numbers associated with a supplier. Each entry includes comment, extension, label, and number.  |
| supplierId  | String  | The unique identifier of a supplier in the Arena database  |
| website  | String  | The website of a supplier  |

