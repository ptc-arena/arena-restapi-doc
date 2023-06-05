# Errors When Creating Items 
POST /items

The Item Creation Process starts when an Onshape part that is assigned an Arena reserved item number is synced with Arena. Both the part that is being created and the reserved number have to be assigned the same Item Category. Otherwise a new reserved item number must be requested by Onshape. Reserved item numbers that are used to create parts are removed from the reserved numbers that are stored internally in Arena. This process allows assignment of core and custom attribute information.

The POST /items endpoint is used to create Onshape Parts in Arena with basic and attribute information using a reserved number stored internally in Arena. The POST /login and POST /login/authorizeuser endpoints are a pre-requisite prior to it’s execution. The Onshape User Arena authorize user must have a Full License, Item Read and Write and File Read and Edit Access Policy Rules in Arena. If the POST /items endpoint fails then the part should not be created


| Status Code  | Error Code  | Message  | Explanation  |
|  --- |  --- |  --- |  --- | 
| 400  | 3024  |  ```Either you do not have privileges to access the requested data or it does not exist.```    |  This issue occurrs when Onshape-Arena user may not have any of the following:<br>   <br> *  Full License<br>    <br> *  Item Read and Write Access Policy Rules<br>    <br> *  File Read and Write Access Policy Rules<br>    <br> *  Prohibited Based On Category, Procurement Type, Lifecycle Phases<br>      User can attempt to create the same type of item directly in Arena to see if they have the required permissions.<br>  Ultimately, the Arena Account Administrator would need to check of the user has the appropriate access in workspace settings.<br>    |
| 400  | 3254  |  ```Item-Number-Reservation-ID does not match reservation.```    | Onshape is attempting to create an Item with a Part Number that has not been reserved in Arena. Onshape User should reserve an item number in Arena.   |
| 400  | 3256  |  ```The item number was reserved with category guid “{0}””{1}”. A different category cannot be specified.```    | Onshape is attempting to create an Item that is assigned a different Item Category than what was assigned at the time the Item Number was reserved in Arena.If the category is changed in Onshape then a new number should be reserved. The previously reserved number will not be used.<br> \{0\} represents the Category GUID.<br> \{1\} represents the Arena Category Name.<br>   |

