# 3300 to 3999 - Arena API Unique Error Codes
The list below details unique API error codes from 3300 to 3999.


| Latest Code  | Historical Code \(Before Winter 2023\)  | Message  |
|  --- |  --- |  --- | 
| 3301  |   |  ```Item "{0}" is not the effective revision or it is not the superseded revision of itself.```    |
| 3302  |   |  ```The Quantity value can't be empty.```    |
| 3303  |   |  ```The Quantity value must be greater than {0}.```    |
| 3304  |   |  ```The Quantity value must be lesser than {0}.```    |
| 3305  |   |  ```The Notes field value cannot exceed {0} characters.```    |
| 3306  |   |  ```Item "{0}" can't be added because it has already been added as a substitute in the BOM line.```    |
| 3307  |   |  ```Rank values must be positive.```    |
| 3308  |   |  ```Rank values cannot be more than {0}.```    |
| 3309  |   |  ```The substitute could not be created.```    |
| 3310  |   |  ```The substitute for "{0}" could not be updated.```    |
| 3311  |   |  ```Either the substitute could not be deleted or the substitute does not exist.```    |
| 3312  |   |  ```The substitute with a rank of {0} could not be created.```    |
| 3313  |   |  ```The substitute "{0}" was created, but we were unable to set the substitute rank to {1}.```    |
| 3314  |   |  ```The substitute for "{0}" with a rank of {1} could not be updated.```    |
| 3315  |   |  ```No attribute need to be updated.```    |
| 3116  |   |  ```Not a valid substitute item, either it's null, or it's invalid item guid.```    |
| 3117  |   |  ```Substitutes are currently not allowed in your workspace. Please contact your Account Administrator for additional information.```    |
| 3318  |   |  ```Item "{0}" is not the effective revision.```    |
| 3119  |   |  ```Invalid substitution. Substitute item can't be the same Item revision as the child Item on the BomLine "{0}".```    |
| 3320  | 3310  |  ```An existing substitute cannot be modified through an update action. Please remove the item as a substitute first.```    |
| 3400  |   |  ```The attribute latestEditionAssociation cannot be set to true because the file specified is not the latest edition.```    |
| 3450  |   |  ```This Ticket currently has references to other objects. Before this Ticket can be deleted, all references must be removed.```    |
| 3451  |   |  ```Ticket number cannot be customized due to template settings.```    |
| 3452  |   |  ```You cannot create a ticket with an inactive template.```    |
| 3453  |   |  ```The specified template does not have a default number format. Please include either numberSequencePrefix or number and resubmit.```    |
| 3454  |   |  ```The number specified is already being used by another Ticket. Please select a different value for number and resubmit.```    |
| 3455  |   |  ```Including both numberSequencePrefix and number is not supported. Please select one of the two options and resubmit.```    |
| 3456  |   |  ```This object has already been added as a reference to this Ticket.```    |
| 3457  |   |  ```When adding unreleased Items as references, latestRevisionAssociation must be set to true.```    |
| 3458  |   |  ```A specific Ticket cannot be added as a reference to itself.```    |
| 3459  |   |  ```Completed Ticket cannot be deleted.```    |
| 3470  | 3134  |  ```Only Markups can be associated to a Change as a Markup.```    |
| 3471  | 3134  |  ```Files can only be added to Open and Unlocked Changes.```    |
| 3472  | 3134  |  ```Files can only be added to unlocked Requests.```    |
| 3473  | 3134  |  ```Files can only be removed from Open and Unlocked Changes.```    |
| 3474  | 3134  |  ```Files can only be removed from unlocked Requests.```    |
| 3475  | 3134  |  ```Implementation Files cannot be added to Completed or Canceled Changes.```    |
| 3476  | 3134  |  ```Implementation Files cannot be removed from Completed or Canceled Changes.```    |
| 3477  | 3139  |  ```Markups cannot be associated to Requests through the Request File endpoint. Please use the appropriate Request Markup endpoint for Markups.```    |
| 3478  | 3139  |  ```Only existing Markups can be associated to a Request as a Markup.```    |
| 3479  | 3139  |  ```The Markup is already associated with another Request and cannot be added to another.```    |
| 3501  |   |  ```The Item Specs view image can only be updated from the working revision of the Item.```    |
| 3502  |   |  ```The Item GUID is not valid in the following locations: {0}.```    |
| 3503  |   |  ```Item GUID or Number is required in the following locations: {0}.```    |
| 3504  |   |  ```Duplicate Item Numbers in the following locations: {0}.```    |
| 3505  |   |  ```The Item Lifecycle Phase GUID is not valid or is not active in the following locations: {0}.```    |
| 3506  |   |  ```Item Lifecycle Phase Name is not valid or it is not active or it is not unique in the following locations: {0}.```    |
| 3507  |   |  ```Item Lifecycle Phase GUID or Lifecycle Phase Name is required in the following locations: {0}.```    |
| 3508  |   |  ```You do not have privilege to do the LCP change in the following locations: {0}.```    |
| 3509  |   |  ```Can't support item.status and item.revisionStatus at the same time, please using item.revisionStatus as the query key.```    |
| 3511  |   |  ```Item Bulk Lifecycle Phase Change does not support input files with more than 25,000 Items. Please reduce the number of Items in the input file to less than or equal to 25,000 Items and resubmit.```    |
| 3512  |   |  ```We are unable to initiate the Item Bulk Lifecycle Phase Change release. Another Item Bulk Lifecycle Phase Change release with guid: "{0}" is in progress. Currently, a workspace can only support one Bulk Item Lifecycle Phase Change release at time. Please wait for the current Bulk Lifecycle Phase Change release to complete before trying again.```    |
| 3513  |   |  ```Item Bulk Lifecycle Phase Change timeout after 100 seconds.```    |
| 3514  |   |  ```Too many running threads.```    |
| 3515  |   |  ```The character length of {0} exceeds the limit due to multibyte characters. Please modify the name accordingly and submit your entry again.```    |
| 3516  |   |  ```Input items do not exist or input item numbers are not unique in the workspace. Please check {0}.```    |
| 3517  |   |  ```This bulk change had already been committed.```    |
| 3518  |   |  ```You cannot commit in this status.```    |
| 3519  |   |  ```You need to set "commit" to true.```    |
| 3520  |   |  ```You cannot get the result now.```    |
| 3521  |   |  ```Invalid status : {0}```    |
| 3522  |   |  ```No file content.```    |
| 3523  |   |  ```Cannot load data.```    |
| 3524  |   |  ```Dataset is empty, please make sure all data put in the first worksheet. The following headers are required: Guid, Item Number, Lifecycle Phase Name, Lifecycle Phase Guid. Revision can optionally be specified.```    |
| 3530  | 3501  |  ```Image file is not valid or exceed the file size limit 10MB.```    |
| 3531  | 3501  |  ```The specified file is not a valid image.```    |
| 3532  | 3501  |  ```The file must be associated with the item (supplier item).```    |
| 3601  |   | \[Dynamic error messagee.\]  |
| 3602  |   | \[Dynamic error messagee.\]  |
| 3603  | 3601  |  ```Invalid reference designator range: {0}. Ranges must follow the format [letter][number]-[letter][number]. Ex: R4-R10.```    |
| 3604  | 3602  |  ```Reference designators must be smaller than 32000.```    |
| 3605  | 3602  |  ```Duplicate reference designator "{0}" not allowed in this workspace.```    |
| 3606  | 3602  |  ```Invalid reference designator: {0}. Reference designators must be entered as a comma separated list using format [letter][number] or [letter][number]-[letter][number] for a range. Ex: R1,R2,R4-R10.```    |
| 3621  |   |  ```The number format could not be created. A number format with that name already exists in this workspace.```    |
| 3622  |   |  ```Could not update the number format because name duplication.```    |
| 3623  |   |  ```Create item number format failed.```    |
| 3624  |   |  ```Update item number format failed.```    |
| 3625  |   |  ```This number format could not be deleted. Number formats already used by items cannot be deleted.```    |
| 3626  |   |  ```This number format could not be deleted.```    |
| 3627  |   |  ```The auto-generated sequence field could not be added because the pre-defined code list could not be found.```    |
| 3628  |   |  ```This number format is locked from editing. Additional item number format fields cannot be added.```    |
| 3629  |   |  ```The number format field could not be added. Number formats already used by Items cannot be modified.```    |
| 3630  |   |  ```The number format field could not be defined. A number format field with that name already exists in this number format.```    |
| 3631  |   |  ```The maxLength must be an integer between 1 and 200.```    |
| 3632  |   |  ```The value length must be less or equal than 200.```    |
| 3633  |   |  ```The possibleValues.value length must be less or equal than 200.```    |
| 3634  |   |  ```The maxSeqLength must be an integer between 1 and 200.```    |
| 3635  |   |  ```The nextNumber {0} exceeds maxSeqLength limit {1}.```    |
| 3636  |   |  ```This number format already contains 10 fields; no additional fields can be added.```    |
| 3637  |   |  ```The auto-generated sequence field could not be added because an auto-generated Sequence field already exists within this number format.```    |
| 3638  |   |  ```The number format field could not be deleted from this number format because number formats already used by items cannot be modified.```    |
| 3639  |   |  ```This number format is locked from editing. The existing item number format field cannot be deleted.```    |
| 3701  |   |  ```Task name cannot be empty.```    |
| 3702  |   |  ```Task name cannot be empty or more than 100 chars.```    |
| 3703  |   |  ```Implementation task note cannot be updated.```    |
| 3704  |   |  ```Implementation Files cannot be added to Completed or Canceled Changes.```    |
| 3705  |   |  ```Implementation task Files cannot be removed from Completed or Canceled Changes.```    |
| 3851  |   |  ```The attributes assemblyType and inAssembly cannot be used simultaneously within the same endpoint URL. Since the information for both search attributes can be inferred from the results in assemblyType, use assemblyType by itself within the endpoint URL instead.```    |
| 3852  |   |  ```Invalid assemblyType: {0}```    |
| 3991  |   |  ```This Request has already been added to the Change.```    |
| 3992  |   |  ```Only Promoted Requests can be added to a Change.```    |
| 3993  |   |  ```Requests can only be added or removed from an Open and Unlocked Change.```    |

