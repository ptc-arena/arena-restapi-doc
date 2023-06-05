# API Format
The Arena API is based on a REST architecture and transfers JSON content exclusively \(except for file content operations, which are JSON and multipart/form-data.\) 

A user's base API URL can differ depending on what URL they use to access their workspace.

**If the user's workspace is accessed through https://app.bom.com, the base API URL is https://api.arenasolutions.com/[version].** 

For example, a request to return all Items in a workspace would be 

https://api.arenasolutions.com/v1/items.

**If the user's workspace is accessed through https://app.arenagov.com, the base API URL is https://api.arenagov.com/[version].** 

For example, a request to return all Items in a workspace would be

https://api.arenagov.com/v1/items.

**If the user's workspace is accessed through https://app.europe.arenaplm.com, the base API URL is https://api.europe.arenaplm.com/[version].** 

For example, a request to return all Items in a workspace would be 

https://api.europe.arenaplm.com/v1/items.

The user constructs JSON requests to specific URL endpoints on the Arena API service. The API service responds with data, in the case of a GET request, or updates the workspace in the case of a POST request. You can also perform PUT and DELETE requests to specific URLs.

This document includes details about requests and responses from Arena servers, and instructs developers in how to construct requests. This document assumes some familiarity with APIs in general.

| A Note on JSON inputs: When constructing Requests to the API service, please follow best practices for JSON data types: <br> *  Text values should be in quotes \("text"\)<br>    <br> *  Numeric values should not be in quotes \(42\)<br>    <br> *  Null values should not be in quotes \(null\)<br>    <br> *  Boolean values should be only true or false \(true\)<br>    <br> *  Internal quotes in values  should be escaped with the \ character \(18\"\).<br><br>    <br> *  Dates \(2012-01-12T19:22:27Z\)<br>    <br> *  GUID values should be in quotes \("2K4N1Y24FWFN6LDUC67B"\)<br>       |
|  --- | 

Each Arena object is represented by a GUID \(Globally Unique IDentifier\). When you perform a GET, you receive object GUIDs in return, and use those GUIDs to specify objects on which you perform actions.

So, you might perform a GET to determine the GUID of a particular Item, and then perform a PUT specifying that Item’s GUID to update its specification data.

Arena’s approach to a REST API distinguishes between two types of entities: an object itself \(such as an item or file\) and the relationship between two objects \(such as a BOM line or file association.\) This approach allows users to specify attributes both for the object and for the relationship. 

For example, the attributes of an item might include, name, number, etc—but when that item is being added to a BOM, you need to specify attributes about the relationship between the item and its parent \(which might include quantity, reference designators, etc.\)

All Date and Time formats in the Arena REST API are Zulu format: "2014-07-07T23:19:46Z” YYYY-MM-DDTHH-mm-ssZ \(YYYY is 4 digit year, MM is two digit month, DD is two digit day, HH is 2 digit 24 hr hour, mm is 2 digit minute, ss is 2 digit second\)

