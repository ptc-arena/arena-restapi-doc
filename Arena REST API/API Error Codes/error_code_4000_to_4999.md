# 4000 to 4999 - Arena API Unique Error Codes
The list below details unique API error codes from 4000 to 4999.

Error codes within the range of 4000 to 4099 focus on Changes, Requests, Training Plans, and User Group objects.


| Latest Code<br> | Historical Code \(Before Winter 2023\)<br> | Message<br> |
|  --- |  --- |  --- | 
| 4000<br> |   |  ```Only Open and Unlock Change can add the Requests.```  |
| 4001<br> |   |  ```Item lifecycle phase has been changed.```  |
| 4002<br> |   |  ```Unreleased item cannot be added to a temporary change.```  |
| 4003<br> |   |  ```All views must be included for unreleased items.```  |
| 4004<br> |   |  ```Unreleased item must be released to In Design or In Production stage.```  |
| 4005<br> |   |  ```The item is already in the change.```  |
| 4006<br> |   |  ```End revision number cannot be empty.```  |
| 4007<br> |   |  ```Selected view is already in another change.```  |
| 4009<br> |   |  ```{0}.includedInChange cannot be set to true because the {1} view of this item is already included in a change.```  |
| 4010<br> |   |  ```Error adding disposition attributes.```  |
| 4011<br> |   |  ```Invalid number format prefix.```  |
| 4012<br> |   |  ```The number format prefix is required.```  |
| 4013<br> |   |  ```The change is locked, inaccessible or invalid.```  |
| 4014<br> |   |  ```The default value for Effectivity Type is enforced for Changes assigned to this category and cannot be edited.```  |
| 4015<br> |   |  ```A new prefix cannot be selected because the default number sequence is enforced for Changes assigned to this category.```  |
| 4016<br> |   |  ```Default number sequence is enforced for Changes assigned to this category, but no default sequence has been specified.```  |
| 4017<br> |   |  ```This Change cannot be assigned to the specified category because the enforced default effectivity of the category is not allowed.```  |
| 4018<br> |   |  ```This Change cannot be assigned to the specified category because once created, a Change cannot move to a different number sequence.```  |
| 4019<br> |   |  ```Effectivity cannot be modified because once created, a Change cannot move between permanent and temporary effectivity.```  |
| 4020<br> |   |  ```The change cannot be updated at this lifecycle stage.```  |
| 4021<br> |   |  ```Item revision is automatically generated for items of this category and cannot be entered manually.```  |
| 4022<br> |   |  ```The category settings of this Change does not allow duplicate revision values. Please ensure that the New Revision value is unique.```  |
| 4023<br> |   |  ```The "retrainingRequired" attribute is only valid in a request if the Item is already released and already associated with an existing Training Plan.```  |
| 4024<br> |   |  ```The attribute "retrainingRequired" can only be used with Items that are already associated with an existing Open Training Plan.```  |
| 4025<br> |   |  ```newItemRevision must be the working revision of the item.```  |
| 4026<br> |   |  ```On released items, notes can only be added if {0}.includedInThisChange is true.```  |
| 4027<br> |   |  ```{0}.includedInThisChange must be explicitly set to true to add notes.```  |
| 4028<br> |   |  ```Unreleased items must have {0}.includedInThisChange set to true.```  |
| 4029<br> |   |  ```routings cannot be specified.```  |
| 4030<br> |   |  ```The request is locked, inaccessible or invalid.```  |
| 4031<br> |   |  ```The request evaluator group guid "{0}" is not valid.```  |
| 4032<br> |   |  ```The request code value "{0}" is not valid.```  |
| 4033<br> |   |  ```The Request cannot be deleted because it has been added as an affected object in at least one Quality Process.```  |
| 4034<br> |   |  ```The Request cannot be deleted because it has been added as a reference in at least one Project.```  |
| 4035<br> |   |  ```The Request cannot be deleted because the status is either SUBMITTED or PROMOTED.```  |
| 4036<br> |   |  ```The evaluator group is required.```  |
| 4037<br> |   |  ```The Request cannot be deleted because current user is not a Request Administrator.```  |
| 4038<br> |   |  ```Invalid prefix. When updating a Request number, the user can only use prefixes supported by the original Request number sequence.```  |
| 4039<br> |   |  ```Items can only be added to unlocked Requests.```  |
| 4040<br> |   |  ```The Notes field value cannot exceed {0} characters.```  |
| 4041<br> |   |  ```Invalid item revision guid, only the effective revision of a released item or the working revision of an unreleased item are allowed.```  |
| 4042<br> |   |  ```This item has already been associated to this Request.```  |
| 4043<br> |   |  ```Items can only be updated under unlocked Requests.```  |
| 4044<br> |   |  ```Only request administrators can execute this specific request lifecycle transition.```  |
| 4045<br> |   |  ```The attribute "{0}" can only be updated when transitioning a request into the DEFERRED lifecycle status.```  |
| 4046<br> |   |  ```The attribute "{0}" can only be updated when transitioning a request into the PROMOTED or CLOSED lifecycle status.```  |
| 4047<br> |   |  ```The deferDeadlineDateTime value within the request body must be a date and time that exists after the date and time the endpoint is submitted.```  |
| 4048<br> |   |  ```The deferralCode value is not a valid option within this workspace.```  |
| 4049<br> |   |  ```A valid "{0}" is required when transitioning a request from the "{1}" lifecycle status to the "{2}" lifecycle status.```  |
| 4050<br> |   |  ```The resolutionNotes attribute can only be used by users promoting or closing requests created by supplier users.```  |
| 4051<br> |   |  ```The attribute "status" is required and the value must not be null in the payload.```  |
| 4052<br> |   |  ```{0} must be smaller than {1}.```  |
| 4060<br> | 4002<br> |  ```Unreleased item {0} cannot be added to a temporary change.```  |
| 4061<br> | 4005<br> |  ```The Items you selected cannot be added due to a conflict with an existing Change.```  |
| 4062<br> | 4029<br> |  ```This Change is locked. Edits can be performed only on Open and Unlocked Changes.```  |
| 4063<br> | 4029<br> |  ```Can only be called if the change is Open and Unlocked.```  |
| 4064<br> | 4029<br> |  ```Items can be deleted only when the change is Open and Unlocked.```  |
| 4065<br> | 4029<br> |  ```Revision number could not be auto-generated and must be set manually.```  |
| 4066<br> | 4029<br> |  ```Revision number must be non-empty and can't exceed {0} characters long.```  |
| 4067<br> | 4043<br> |  ```Items can only be deleted from unlocked Requests.```  |
| 4068<br> | 4048<br> |  ```The resolutionCode value is not a valid option within this workspace.```  |
| 4071<br> | 4001<br> |  ```Item lifecycle phase has been changed.```  |
| 4072<br> | 4002<br> |  ```This request cannot be converted to an object.```  |
| 4073<br> | 4003<br> |  ```The value for the attribute "{0}" is not valid.```  |
| 4074<br> | 4004<br> |  ```The attribute "{0}" is not recognized.```  |
| 4075<br> | 4005<br> |  ```The object with guid "{0}" is deleted successfully.```  |
| 4076<br> | 4006<br> |  ```You have successfully logged out.```  |
| 4077<br> | 4007<br> |  ```The file with guid "{0}" cannot be downloaded at this time.```  |
| 4078<br> | 4008<br> |  ```The requested file with guid "{0}" does not have any content. Please make sure it is a valid file.```  |
| 4079<br> | 4009<br> |  ```API feature is not enabled in your workspace.```  |
| 4080<br> | 4010<br> | \[Currently No Message\]<br> |
| 4081<br> | 4011<br> |  ```Your password has either been reset by an Account Administrator or has expired. Please proceed to the browser-based Arena user interface and configure a new password.```  |
| 4082<br> | 4012<br> |  ```Access not allowed.```  |
| 4083<br> | 4013<br> |  ```Too many invalid password attempts, account disabled for five minutes.```  |
| 4084<br> | 4014<br> |  ```You have exceeded your maximum of "{0}" requests during the last 24 hours. Additional requests can be made at "{1}".```  |
| 4085<br> | 4015<br> |  ```Unexpected data access error, please contact support.```  |
| 4086<br> | 4016<br> | \[Dynamic Error Message\]<br> |
| 4087<br> | 4017<br> |  ```Unknown errors encountered. Please contact Arena Technical Support{0}.```  |
| 4088<br> | 4018<br> | \[Dynamic Error Message\]<br> |
| 4089<br> | 4019<br> |  ```Invalid token.```  |
| 4090<br> | 4020<br> |  ```The Onshape feature is not enabled in your workspace.```  |
| 4201<br> |   |  ```Number of question required is too small.```  |
| 4202<br> |   |  ```Number of correct answer required is too small.```  |
| 4203<br> |   |  ```Need more questions.```  |
| 4204<br> |   |  ```Need more answers.```  |
| 4205<br> |   |  ```Invalid Quiz Id.```  |
| 4206<br> |   |  ```Invalid Quiz Attempt Id.```  |
| 4207<br> |   |  ```Quiz was not found.```  |
| 4208<br> |   |  ```Too many questions.```  |
| 4209<br> |   |  ```Too many answers in a question.```  |
| 4210<br> |   |  ```Number of questions is too big.```  |
| 4211<br> |   |  ```Number of required questions is too big.```  |
| 4212<br> |   |  ```Invalid item id.```  |
| 4213<br> |   |  ```Content is too long.```  |
| 4214<br> |   |  ```Content cannot be empty.```  |
| 4215<br> |   |  ```Training is not enabled for this user.```  |
| 4216<br> |   |  ```Only training managers can create a training plan.```  |
| 4217<br> |   |  ```Only the assigned training manager for this training plan can perform this action.```  |
| 4218<br> |   |  ```The training plan has already in status "{0}".```  |
| 4219<br> |   |  ```This user has already been added to this training plan.```  |
| 4220<br> |   |  ```The due date cannot be set because there is no item in this training plan.```  |
| 4221<br> |   |  ```This item cannot be added to this training plan. Training plans can only contain a maximum of 200 items.```  |
| 4222<br> |   |  ```Only the effective revision of a released item can be added to a training plan.```  |
| 4223<br> |   |  ```This quality process step has already been added to this training plan.```  |
| 4224<br> |   |  ```Disabled user cannot be added to the training plan.```  |
| 4225<br> |   |  ```Quality process sign-off steps cannot be added to a training plan.```  |
| 4226<br> |   |  ```This item has already been added to this training plan.```  |
| 4227<br> |   |  ```Only designated training managers can assign a training manager for a training plan.```  |
| 4228<br> |   |  ```Only training managers can update a training plan.```  |
| 4229<br> |   |  ```Only the opened training plan can perform this action.```  |
| 4330<br> |   |  ```Only user in training manager list can be selected as a manager.```  |
| 4301<br> |   |  ```No permission to get the integration and integration associated information.```  |
| 4302<br> |   |  ```No permission to create the integration and integration associated information.```  |
| 4303<br> |   |  ```You currently do not have permission to mark this object as reconciled or to be reconciled.``` ```Please contact your Account Administrator for more information.```  |
| 4310<br> |   |  ```This endpoint is not supported for outbound integrations with Change-Based transfer types.```  |
| 4320<br> |   |  ```The itemsReconciled value is null or not valid, please use: true/false.```  |
| 4321<br> |   |  ```The reconciled value is null or not valid, please use: true/false.```  |
| 4322<br> |   |  ```The specified value "{0}" is not valid for the itemsReconciled field. Currently, only the values "true", "false", or "any" can be used for the itemsReconciled field.```  |
| 4323<br> |   |  ```The value "{0}" is not valid for date and time fields. Please format all date and time fields in UTC/Zulu format.```  |
| 4324<br> | 4322<br> |  ```The specified value "{0}" is not valid for the resourcesReconciled field. Currently, only the values "true", "false", or "any" can be used for the resourcesReconciled field.```  |
| 4325<br> | 4322<br> |  ```The specified value "{0}" is not valid for the reconciled field. Currently, only the values "true", "false", or "any" can be used for the reconciled field.```  |
| 4326<br> | 4322<br> |  ```The creationDateTimeFrom value: "{0}" cannot be later than creationDateTimeTo value: "{1}".```  |
| 4327<br> | 4322<br> |  ```The reconciledDateTimeFrom value: "{0}" cannot be later than reconciledDateTimeTo value: "{1}".```  |
| 4328<br> | 4322<br> |  ```The offSet value: "{0}" is not valid.```  |
| 4329<br> | 4322<br> |  ```The limit value: "{0}" is not valid.```  |
| 4399<br> |   |  ```Server exception: {0}.```  |
| 4501<br> |   |  ```The Supplier Identifier "{0}" matches an existing Supplier Identifier in the workspace. Due to current workspace settings, the Supplier Identifier attribute must be unique for each Supplier.```  |
| 4701<br> |   |  ```Name "{0}" matches an existing User Group Name in the workspace. Names must be unique.```  |
| 4808<br> |   |  ```Trace Matrix maximum limit exceeded.```  |
| 4809<br> |   |  ```Trace Coverage maximum limit exceeded.```  |
| 4897<br> |   |  ```Permanent changes cannot transition to the EXPIRED lifecycle status.```  |
| 4898<br> |   |  ```This Change has errors that render it no longer valid.```  |
| 4899<br> |   |  ```Temporary changes cannot transition to the EFFECTIVE lifecycle status from the COMPLETED lifecycle status.```  |
| 4900<br> |   |  ```Currently, implementationStatus can only be updated when transitioning into the following change lifecycle statuses: COMPLETED, EFFECTIVE, and EXPIRED.```  |
| 4901<br> |   |  ```The action could not be completed because either the Change or the BOM of one or more Items contains hidden Items (Items to which you do not have access.) Please contact your Account Administrator.```  |
| 4902<br> |   |  ```The requested change lifecycle transition can only be performed by a change administrator.```  |
| 4991<br> |   |  ```Invalid change administrator guid "{0}".```  |
| 4992<br> |   |  ```The change requires at least one change administrator.```  |
| 4993<br> |   |  ```Only change administrators can execute this specific change lifecycle transition.```  |
| 4994<br> |   |  ```Additional change submission errors exist. Only the first twenty errors are presented here for the user's convenience.```  |
| 4995<br> |   |  ```This specific change lifecycle transition does not support the inclusion of a change administrator in the request body.```  |
| 4996<br> |   |  ```The resulting change lifecycle status (and the overall change lifecycle path) is determined by the routing method configured in workspace settings. In order to submit this change, input "SUBMITTED" for status in the request body.```  |
| 4997<br> |   |  ```Only a change administrator or the user who submitted the change can perform this action.```  |
| 4998<br> |   |  ```This change cannot transition to the COMPLETED lifecycle status due to open implementation tasks.```  |
| 4999<br> |   |  ```Invalid implementation status. It could be: NOT_STARTED, IN_PROGRESS, NEEDS_ATTN, DONE, BLANK.```  |

