

# Arena REST&#160;API

The Arena REST API lets you link your Arena workspace to other systems and exchange data using a RESTful framework. You'll find detailed information about all available objects and endpoints in the table of contents in the left pane.

If you have any comments or questions about the Arena REST API, contact us at [Arena-support@ptc.com](mailto:Arena-support@ptc.com?subject=Feedback from API help page).

## What's New?

**May 20, 2023**

<span style="font-weight: bold;font-style: normal;">Attention All Arena REST&#160;API users</span>: Following RFC 2616 section 4.2, Arena REST API HTTP header names will become case-insensitive in an imminent release. To prepare for this modification, we encourage all Arena REST API users to check their code to ensure it can accept case-insensitive HTTP headers. If your code is not compatible with this change, it may cause issues with your integration. Please stay tuned for future updates.

Users can now import item specs amd item BOM information through the Import Engine. Broadly speaking, the Import Engine uses a POST Definition endpoint to configure an import. Next a POST Run endpoint uses a Definition GUID and a source file with valid content to import the data into an Arena workspace. Supplementary GET and PUT endpoints for Definition and Run endpoints are also available.

Arena REST API now supports endpoints for searching, creating, editing (assignee and status), and removing Change Implementation Tasks. Additional endpoints that support searching, creating, editing and removing of Change Implementation Task notes and Change Implementation Task files are also included.

To delineate between global Inventory Disposition settings and category-specific Inventory Disposition settings, the Change Item Attribute object now supports a new property labeled global. The property global is a boolean attribute. Core attributes and categories set to Global Requirements return a value of true for global. Attributes with one or more categories set to Category Specific Requirement Rules return a value of false for global.  A new settings endpoint GET /settings/changes/categories/GUID/items/attributes returns change category-specific item attributes.

In order to support customizable Abandoned, Deprecated, and Obsolete phases, the Item Lifecycle Phase object now uses a new property called type that primarily appears within the GET /settings/items/lifecyclephases endpoint.
Additionally the POST /items/lifecyclephasechanges, POST /changes/GUID/items, and the PUT /changes/GUID/items/GUID endpoints now support direct revisioning of the Abandoned, Deprecated, and Obsolete lifecycle phases.

The GET Tickets Templates and GET Quality Process Templates endpoints now support two new search attributes: name and active.  The attribute name allows the user to search by the name of the template. The attribute active is a boolean attribute. If active is set to true, the endpoint searches for active templates.

The GET /items and GET /items/GUID endpoints now support a new parameter labeled responseview. The new parameter responseview allows users to customize the response data from the two GET items endpoints. By setting responseview to a specific value, users can change the default data for each GET items endpoint.

The GET, POST, and PUT endpoints that reference Change resources now return a new property labeled url. Url returns two references that are direct urls for the Change resource: api and app. App stands for application and is the direct url link to the Change resource in the main Arena user interface application. The responses in the following GET, POST, and PUT endpoint groups have been updated to reflect the new url property: Changes, Changes Status Workflow, change-based Event Queue (Outbound Integrations), and change-based Event Engine (Outbound Events). Note that the url property was added for items endpoints in April of 2022.

The POST changes/GUID/items endpoint no longer requires the newLifecyclePhase attribute within the request body. Omitting the newLifecyclePhase attribute from this endpoint automatically selects the scheduled lifecycle phase based on its current phase.

**January 8, 2023**

Arena REST API capability expands to the Request view of a Change and includes the following new endpoints:

*   Ability to perform a general search for the Requests to a specific Change.
*   Ability to perform a GUID search for a specific Request to a specific Change.
*   Ability to add a Request to a specific Change.
*   Ability to remove a Request from a specific Change.

Arena REST API also now includes two new endpoints for searching Changes associated with a Request:

*   Ability to perform a general search for Changes associated to a specific Request.
*   Ability to perform a search by GUID for a specific Change associated to a Request.

With Event Engine support for Requests, Arena REST API now includes the following endpoints:

*   Ability to perform a general search for Request related events from a specific event in a specific outbound-event integration.
*   Ability to perform a search for a specific Request event from a specific event in a specific outbound-event integration.
*   Ability to reconcile or unreconcile a Request specific event.

In addition to the above endpoints, the existing GET Triggers, GET Outbound-Event Integration Triggers, and the GET Outbound-Events Integration Events endpoints (and their specific variants) now support the Request world.

To support the new After Approval option for Retrain when adding Training Plan Items to a Change, a new retraining attribute is now included in the Change Affected Item object used in GET Change Items, GET Change Item, POST Change Items, and PUT Change Items. The retraining attribute supports the values NO_RETRAIN, AFTER_APPROVED, and AFTER_EFFECTIVE. The existing retrainingRequired attribute is used in the GET endpoints, but not in the request body for the GET POST Change Items and PUT Change Items endpoints.

GET Items now supports the assemblyType attribute in general Items search. Additionally inAssembly and assemblyType are now included in the Item objects for the GET Items and the GUID specific GET Items search. For  more details see the Winter 2023 release notes.

The GET Request Attributes and GET Request Category Attributes now include support for editable Request core attributes.

Developers can now set specific attributes to null through a PUT endpoint. To set an attribute to null, users can append the PUT endpoint with "setnull=true". The table below summarizes the attributes that can be set to null. For for more details see the Winter 2023 release notes

To better assist Arena API developers, API error codes are now unique. Previously, duplicate error codes represented different errors. In conjunction with the Arena-Onshape integration, a new section of Arena Help now details 59 errors that deal with possible Arena-Onshape integration issues with item and login endpoints. While introduced as possible errors for the Arena-Onshape integration, the error codes also apply to errors for item and login Arena API endpoints. A table that compares the old error codes with new error codes is available in Arena Help. A more complete and detailed list of possible API error codes will be included in future releases.

**June 26, 2022**

*   Creating, editing, searching (general), searching (specific by GUID), deleting, and modifying the status of a Training Plan.
*   Adding, searching (all in Items view), searching (specific by GUID), and removing Items from the Items view of a Training Plan.
*   Adding, searching (all in Users view), searching (specific by GUID), editing, and removing users from the Users view of a Training Plan.
*   Adding, searching (all objects in Files view), searching (specific by GUID), and removing Files from the Files view of a Training Plan.
*   Adding, searching (all Quality Processes in the References view), searching (specific by GUID), and removing Quality Processes from the Reference view of a Training Plan.
*   Searching for all records in the Records view of a Training Plan and for searching for a specific record (by GUID) within the Records view of a Training Plan.
*   Settings endpoints that return all the training managers within a workspace or a specific training manager from a workspace.
*   Setting endpoints that return all the training plan number sequences with a workspace or a specific training plan number sequence within a workspace.
*   Item endpoints that return all training plans that include the item or a specific training plan that includes that item.
*   File endpoints that return all training plans that include the File or a specific training plan that includes that File.
*   Lastly, the existing GET Quality Process Step Affected Objects endpoints now return Training Plans that include the Quality Process as a reference.

Arena REST API capability expands to Request workflows. The expansion includes new POST workflow endpoints and a supporting GET call that aids in modifying a Request workflow:

*   Submitting a Request.
*   Withdrawing a Request.
*   Deferring a Request.
*   Promoting a Request.
*   Closing a Request.
*   A GET endpoint that returns the request attributes used when a request undergoes a lifecycle status change.

Arena REST API capability expands to additional Change workflow functions. Additionally, a new  GET endpoint returns the implementation statuses that can be used when completing a change. New POST Change status endpoints support the following POSTfunctions:

*   Withdraw a Change.
*   Force approve a Change.
*   Force reject a Change.
*   Cancel a Change.
*   Reopen a Change.
*   Force expire a Change with temporary effectivity (also known as a Deviation).
*   Complete an effective Change with an option to also update the implementation status.
*   Unmark a Change as completed.
*   A GET endpoint that returns the implementation statuses that can be used when completing a Change.

The GET BOM endpoint article now includes a parameter labeled includeAdditionalAttributes. If included in the endpoint and set to true, additional attributes (also called BOM attributes) are included in the response for each child item.

GET category attribute endpoints for Items, Changes, and Requests include a new attribute field labeled origin. Origin returns information on the inheritance of an Attribute object. When used in conjunction with the global field, users can determine if an object attribute originates from inheritance from a parent category, from being defined in the object category, or from being defined as a global attribute. Origin consists of a GUID and a name field.


**April 17, 2022**

*   The GET, POST, and PUT endpoints that reference Item resources now return a new property url. Url returns two references that are direct urls for the Item resource: api and app. App stands for application and is the direct url link to the Item resource in the main Arena user interface application. The responses in the following GET, POST, and PUT endpoints have been updated to reflect the new url property:  Item (Including Item Criteria), BOM (BOM Line), Item Revisions, Item Where Used, Item Lifecycle Phase Change, Change Items, Request Items, and Supplier Item Sourcing.

**January 14, 2022**

*   Arena REST API capability has been expanded to include a new POST endpoint that allows users to modify the status of a Change. The POST Status Changes endpoint allows users to perform the following actions: Lock and Unlock a Change, Submit a Change for Approval, and Submit a Change for Routing (Admin-Defined Routing Method.
*   A new GET Change Alerts endpoint allows users to look up errors and notices that occur when attempting to submit a Change. Lastly, a new GET Change Administrator endpoint allows users to retrieve all the Change Administrators within a workspace.
*   A new GET Export Settings Attributes endpoint returns the export attributes supported when creating an Export Definition.
*   Arena REST API capability has been expanded to include a GET endpoint that returns the decisions of all users in a Quality Process sign-off step. Additionally, a GET endpoint that returns the specific decision of a user in a specific Quality Process step is available.
*   The GET Supplier Item Sourcing endpoint, which returns all the source relationships of a Supplier Item, now includes the GUID for each source relationship within the response body. If the GET Supplier Item Sourcing endpoint is appended with a valid GUID, it now returns the specific source relationship of a specific Supplier Item.
*   Arena REST API capability has been expanded to include five GET endpoints that return Quality Processes associated with an Item, Supplier Item, Change, or Request. Additionally, GET endpoints that return a specific Quality Process association with an Item, Supplier, Supplier Item, Change or Request are also supported.
*   Arena REST API capability has been expanded to include two GET endpoints that return Ticket objects that appear within the Tickets view of an Item or a Change. If a valid GUID is appended to these endpoints, a specific Ticket associated with an Item, or a Change will be included in the response. Additionally, the existing GET Quality Process Step Affected Object endpoints now returns Tickets that have been added as affected objects to a Quality Process.
*   Arena REST API capability has been expanded to include Requests as affected objects for Quality Processes. Existing GET Quality Processes Step calls will return Requests if the Quality Process step specified contains Requests as affected objects. Existing POST and PUT Quality Process Step calls can be used to add a Request as an affected object to a Quality Process Step or update an existing affected Request within a Quality Process step. Finally, the existing Delete Quality Process Step Affected Object endpoint can now be used to remove Requests as an affected object from a Quality Process step.
*   Triggers with edit actions now create events based on the pre-event state of the category, edited attributes, and the conditions of the resource. For example: A trigger with a resource of Item, an action of Edit, a category of Capacitor, an edited attribute of category, will generate an event if a user edits an Item's category from Capacitor to Resistor. Previously triggers created events in the post-event state.

**October 3, 2021**

*   Arena API now supports Requests. Added five new endpoints that support searching, creating, editing, and deleting Requests. Added five new endpoints that support the searching, adding, editing, and removal of Items from Requests. Added 8 new endpoints for searching, adding, and removal of Files and File Markups to Requests. Added eight new endpoints that return the administrative settings of Requests.
*   Arena API now supports Tickets. Added six new endpoints that support searching, creating, editing, deleting, and updating the status of Tickets. Added four new endpoints that support the searching, adding, and removing of Files to tickets. Added sixteen new endpoints that support the searching, adding, and removal of Changes, Items, Quality Processes, and other Tickets as references to Tickets. Added five endpoints that return the administrative settings of Tickets.
*   Added two new endpoints that allow users to search for the future Changes of an Item. These are the changes listed in the Future Changes subview, Revisions view of an Item.
*   Arena API now supports BOM Substitutes modification. Added five new endpoints that allow users to search, create, update, and remove BOM Substitutes.
*   Arena API supports the new Events Engine feature. Added two new endpoints that support searching for Triggers. Added five new endpoints that support searching for Outbound-Event Integrations, the triggers associated with the Outbound-Event integration, and the Outbound-Event integration administrators. Added two endpoints that support searching for events queued by  Outbound-Event integrations. Added six endpoints that search and specify GUIDs of Items, Changes, and Quality Process of specific events. Added three PUT endpoints that allow users to reconcile or unreconcile the resource specific events.
*   Arena API Help now documents twenty endpoints that allow for the creation, update, and deletion of Item attributes and category attributes. Also included are endpoints that allow creation and editing of categories. These endpoints can be executed by an Account Administrator or a non-Account Administrator user with the appropriate Workspace Settings access policies. These are located in the Items Specs Attributes, Item Categories, and Item&#160;Categories Attributes in the Settings section of endpoints. <span style="font-weight: bold;font-style: normal;">Warning: While supported and documented, Arena does not recommend using these endpoints as it can have significant impact on the product data within your workspace.</span>
*

**August 22, 2021**

*   Arena Help now includes documentation for the GET Items (Search) Criteria Parameter. The GET Items (Search) Criteria Parameter is a special variation of GET Items (Search) that uses the criteria search parameter that merits its own page. It requires URL encoding of the query string. It allows users to search by creation date and create complex queries using the same attributes and operators as API Export.

**April 24, 2021**

*   Added four new endpoints that support searching for Change Files, searching for a specific Change File, creating an association between an existing File and a Change, and deleting an association between a Change and a File. These new endpoints use Change GUIDs as a starting points to interact with files and should not be confused with existing endpoints that use File GUIDs as starting points to interact with Changes.
*   Added four new endpoints that support searching for Change Implementation Files, searching for a specific Change Implementation File, creating an association between an existing File and the Implementation view of a Change, and deleting an association between the Implementation view of a Change and a File. (Files can be associated to Changes in two places: the Files view and the Implementation view.)
*   Added six new endpoints that support searching for File Markups, searching for a specific File Markup, retrieving the content of a File Markup, creating a File Markup, editing a File Markup, and deleting a File Markup.
*   Added four new endpoints that support searching for Change File Markups, searching for a specific Change File Markup, creating a Change File Markup, and deleting a Change File Markup.
*   Added five new endpoints that support searching for Supplier Files, searching for a specific Supplier File, creating an association between an existing File and a Supplier, deleting an association between a Supplier and a File, and deleting a Supplier File.
*   Added two new endpoints that support completing a Quality Process step and reopening a Quality Process step.
*   API Item Export now supports export files in JSON format. In order to facilitate this, a new export option called format can be included when creating Export Definitions. The new export option format supports two values: csv and json. If format is omitted from the export definition, the export assumes a format of csv.

**January 22, 2021**

*   Added three new endpoints for checking out and checking in Files. File Check Out and Check In endpoints are executed by two POST endpoints. A third POST endpoint, Cancel File Check Out, allows users to cancel a File Check Out.
*   Added four new endpoints for Item and Supplier Item compliance. Two new POST endpoints allow users to apply compliance requirements to Items and Supplier Items respectively. Two new DELETE endpoints allow users to remove compliance requirements from Items and Supplier Items.*   Added eight new endpoints for creating, editing, and deleting Item and Supplier Item thumbnail images. For both Items and Supplier Item thumbnail image creation, a second POST endpoint is available which allows users to create a thumbnail image from an associated file.
*   Added eight new endpoints for retrieving all User Groups, a specific User Group, employees in User Groups, specific individual employees in User Groups, partners in User Groups, individual partners in User Groups, general users in a User Group, and a specific user in a User Group.
*   Added two new PUT endpoints for assigning users and assigning User Groups to a Quality Process step. The previous endpoint for assigning a user to a Quality Process step is deprecated.
*   Added ten new endpoints for retrieving, creating, editing and deleting Supplier phone numbers and Supplier addresses.
*   Added support for updating the storageMethodName when updating unlocked files.
*   The GET Export Runs endpoint now supports four new searchable attributes: completionDateTimeFrom, completionDateTimeTo, latestCompleted, number, and status.
*   A new API Export option called <span style="font-weight: normal;font-style: italic;">header </span> allows users to export Items with their attribute names. Previously, all&#160;Item attributes were exported by their apiNames.
*   Export lifecycle status now supports the status of Downloaded. Downloaded indicates that the API export has been downloaded by a user.
*   API Item export now supports the ability to export multiple Items with a revision status of POTENTIAL.

**October 4, 2020**

*   Arena REST API now supports File corrections. Two new GET endpoints allow users to obtain all the corrections to a File or a single specific correction of a File edition. A File correction can be executed through a new POST File Correction endpoint.
*   The Corrected attribute has been added to existing File endpoints.

**September 20, 2020**

*   GET Item Categories no longer includes deleted Categories by default. To include deleted categories a new search parameter, includeDeleted, can be used with the call. To include deleted categories, set includeDeleted equal to true.
*   The component fields within a numberFormat has been changed from apiName to GUID. The numberFormat from GET settings/items/categories/&lt;GUID&gt; can be used to directly create the Item in POST Item Create.

**September 6, 2020**

*   The following fields have been added to the Category, Objects page: deletionDateTime, parentCategory, and structural. The description for assignable has been changed.
*   The GET Item Categories endpoint response examples have been updated with the fields parentCategory, structural, and delationDateTime (for the single deleted category example).

**August 2, 2020**

*   Arena REST API now supports 22 additional Criteria attributes for Arena API Export.
*   The POST Export Definition endpoint article has been updated with the following:

*   modifiedBOM, modifiedSpecs, modifiedFiles, and modifiedSourcing always refers to the working revision since only the working revision is editable.*   Arena Export currently doesn't support export for category.guid using the GUID for uncategorized. The category.guid works for all other categorized GUIDs. To run an export for uncategorized Items use the following criteria: attribute is euqal to category.name, operator is IS_EQUAL_TO, and value is -uncategorized-.
*   <p>An Item Export with revisionStatus set to WORKING or POTENTIAL, will return the working revision of the Items even if these Items contain an efffective, released version.*   The POST Quality Process Step Affected Object Add has been updated and clarified. Items, Changes, Suppliers, Supplier Items, Files, Quality, and URL can be added as an affected object to a Quality Process Step.
            </p>

**April 5, 2020**

*   Arena REST API now supports 10 new endpoints that allow users to monitor the status of outbound integrations and to facilitate the reconcilation of Items within those outbound integrations. Currently only outbound-managed and outbound-automated integrations are supported.
*   Arena REST API capability has been expanded to include 8 new endpoints for Item exports.

*   Exports are defined in an Export definition and are executed in an Export run. Both are POST calls.
*   Similar to Advanced Search in the user interface, users can create complex queries that determine what Items are exported. These structures are called criteria.
*   Currently the following Item views can be exported: Specs, BOM, BOM substitutes, Sourcing, Files, Files-File Summary, Sourcing-Supplier Item Specs, Sourcing-Supplier Item Supplier Profile, Sourcing-Supplier Item Files, and Sourcing-Supplier Item Files-File Summary*   For security reasons, only the user who initiated the export run, can access the export results. All other users will encounter an error.*   Additional notes have been added detailing the behaviour of newItemRevision GUID, affectedItemRevision GUID, and newRevision number in Change Item associations. See GET Change Affected Item endpoint for additional details.

**January 12, 2020**

*   Added support for Multi-Select custom attributes in Changes, Requests, and Quality Processes.
*   For BOM line numbers that are automatically generated (BOM Settings set to automatically generate line numbers), lineNumber will be set to null. BOMs that allow manual editing of line numbers will return line numbers in GET calls.

**August 18, 2019**

*   Ability to add Files and Changes as affected objects to Quality Processes. Added endpoints for creating, editing, and deletin Files and Changes as affected objects for Quality.
*   Added support for Item-To-Item references. Endpoints for creating, editing, and deleting Item-To-Item references are now available.
*   Ability to complete and re-open Quality Processes. Two endpoints for completing &amp; re-opening Quality Processes are now available.

**May 12, 2019**

*   The Arena Rest API has been updated to include support for searching for Items, Supplier Items, Suppliers, Changes, &amp; Quality Processes by custom attributes.

**February 24, 2019**

*   Added support for editable core Item attributes and core Change attributes. When creating or editing Items and Changes, attribute values that violate core property rules for maximum length, format, or requirement rule will cause errors. You can find property settings for core attributes in Settings GET Item Attributes and Settings GET Category Attributes endpoints.
*   Added support for non-revision controlled custom attributes for Items (currently only attributes of field type COST can be non-revision controlled.)
*   Modified meaning of "Required" for custom attributes to match application behavior. Required will now return true for attributes required in the Arena application, even if a default value exists.
*   The deprecated apiName field will now have the value of attribute GUID.
*   Added support for new Allow/Disallow Duplicate Revisions and Allow/Disallow Manual Revision Entry in Change Categories. This affects GET Change Categories.
*   Enumerated editable attributes in PUT Quality Process Step Update.
*   Clarified login credentials for SSO users.
*   Added support for Enforce Default options for Effectivity and Numbering Sequence in Change Categories. This affects GET Change Categories, POST Create Change, PUT Update Change.
*   Updated GET Supplier Attributes and GET Supplier Item Attributes endpoints.
*   Removed multiSelect indicator from custom attributes on non-Item endpoints.
*   Added endpoints for creating, editing, searching, and deleting custom attributes for Suppliers and Supplier Items.
*   Additional Attributes of type NUMBER now accept and return a numeric value (with no quotes) in GET, PUT, and POST endpoints.
*   The fieldType attribute replaces the type attribute in Item attributes and BOM attributes.
*   Support for new multi-select attributes
*   When retrieving Item and Change Additional Attributes via a Settings GET endpoint, the API now returns "required" and "defaultValue" attributes that reflect whether an attribute is global or category-specific.
*   Improved error checking for additional attributes
* Added Affected object for Quality. Fixed typo in sample response of PUT Change Affected Item Edit.


* Small updates from March 11 release. Added more detail about how Change effectivity affects attributes, and how lifecycle phase governs availability of some actions. Reorganized request and response examples in POST Change Create, PUT Change Edit. Separated Table of Contents into Change and Change Item. Various typos etc.


* Added new endpoints to search, create, update, and delete Changes and Change Affected Items.


* Added new GET endpoints to search Changes, Change categories, Change attributes, Change inventory disposition settings, Change routings.



* Added syntax highlighting or "prettified" code samples. Fixed GET Items endpoint to include lifecyclePhase.guid as searchable attribute and corrected Item Number value to be string (not true or false).Fixed GET Item Categories endpoint to clarify that the path parameter is lowercase and that an asterisk must be included after a text string to return all "starts with" results.


* Updated metadata definition for Supplier, Supplier Item, and Quality endpoints. Updated endpoint documentation format to remove redundant Successful/Unsuccessful Response Body sections.


* Fixed some content from June 18 release, including custom attributes of type NUMBER must be submitted as text. Bad URL given for GET Supplier Item Quality Processes and POST Item File Create. Clarified content-type in file creation endpoints.

* Our most recent update (released June 18th, 2017)&#160;made some changes to /settings responses:

* To help API users avoid lengthy debugging, error messaging has been improved to be more specific and descriptive. This update to the Arena REST API also refines the definition of each Arena attribute's properties and enforces stricter validation of each Arena attribute. Some of the properties are being updated for accuracy and properties that are not applicable for an attribute are being removed from responses. Note that, depending on your implementation of the Arena REST API, your code may need to be modified to work correctly.

Previously, these cases were ignored silently, and now fail with an error:

*   submitting invalid attribute or custom attribute names in any request body or query
*   submitting attributes that are not creatable or editable in any POST or PUT request body
*   sending invalid GUIDs in any request body or endpoint

Previously, these /settings endpoints were returning properties that were not applicable (e.g., maxValue and decimalPlaces for text attributes or maxLength for numeric attributes):

*   /settings/items/attributes
*   /settings/items/bom/attributes
*   /settings/files/attributes
*   /settings/quality/attributes
*   /settings/items/categories/&lt;guid&gt;/attributes
