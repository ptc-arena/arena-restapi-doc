# 5000 to 5999 - Arena API Unique Error Codes
The list below details unique API error codes from 5000 to 5999.

Error codes within the range 5000 to 5099 focus on Change Lifeycle errors.


| Latest Code  | Historical Code \(Before Winter 2023\)  | Message  |
|  --- |  --- |  --- | 
| 5001  |   |  ```The approval deadline has not been entered correctly for this Change. If the deadline is enforced, it must be a date in the future (and for a temporary Change, must also precede the expiration date).```    |
| 5002  |   |  ```Effectivity Date has not been entered correctly for this Change. This must be a date in the future.```    |
| 5003  |   |  ```One or more reviewers no longer have a Full or Approver License necessary to approve Changes.```    |
| 5004  |   |  ```Effectivity has not been entered correctly for this Change. The expiration date must fall after the approval deadline.```    |
| 5005  |   |  ```Effectivity has not been entered correctly for this Change. The expiration date must be a date in the future.```    |
| 5006  |   |  ```No routing has been specified for this Change. The Change configuration for this workspace requires that at least one routing be assigned before a Change may be submitted.```    |
| 5007  |   |  ```The decision board for this Change has not been constructed correctly. In the Current Decision subview of the Decisions view, each stage must contain at least one approval role or additional reviewer with an approval requirement of "Unanimous" or "One or More".```    |
| 5101  |   |  ```This Item is being put through a phase change, and this Change includes an effectivity date. This is not allowed. You must remove this Item from this Change, or edit the action being taken on this Item so that it no longer changes phase.```    |
| 5102  |   |  ```This Item is being put through a phase change, and this Change includes an effectivity date. This is not allowed. You must either remove this Item from this Change, edit the action being taken on this Item so that it no longer changes phase, or remove the effectivity date for this Change so that it will become effective upon approval.```    |
| 5103  |   |  ```This Item is contained in a Change that has already been approved, but has not yet become effective. It will not become effective until $target_date. Because of this, this Change can not take effect before that date. You will need to set the effectivity date for this Change to be later than this date or remove this Item from this Change.```    |
| 5104  |   |  ```Inactive Items cannot be included in temporary Changes. You must re-activate this Item or remove it from the Change.```    |
| 5105  |   |  ```The Action specified for this Item is no longer valid due to another Change. You must Edit the Action on the Items view before submitting.```    |
| 5106  |   |  ```The modified Item has required inventory disposition actions that must be selected. Before this Change can be submitted you must go to the Inventory Disposition subview of the Items view and select a Disposition Action for each required Disposition Status.```    |
| 5107  |   |  ```Duplicate revision values are not permitted for this Change category. Please ensure that the New Rev value is unique.```    |
| 5108  |   |  ```Recursive BOM: the Modified Item both contains this child Item and appears in its fully indented BOM. To fix this, you must remove the child Item from the Modified Item's BOM, or remove the Modified Item from this child Item's fully indented BOM.```    |
| 5109  |   |  ```This Item already appears on the BOM and duplicate BOM Items are not allowed in this workspace. If you want to add this Item, remove this duplicate BOM Item and update the Quantity of the existing BOM Item.```    |
| 5110  |   |  ```This working revision of this assembly contains the Item you are Abandoning and is included in an unapproved Change, so the Item cannot be removed from this assembly.```    |
| 5111  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot removed from this assembly.```    |
| 5112  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot be removed from this assembly.```    |
| 5113  |   |  ```This Item is in an active lifecycle phase of the Design stage, so it cannot contain the Abandoned modified Item in its BOM. You must first remove the modified Item from the BOM or remove it from this Change.```    |
| 5114  |   |  ```The modified Item is in the Deprecated phase and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from its BOM, re-activate it, or remove the modified Item from this Change.```    |
| 5115  |   |  ```This Production stage Item cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Production stage Item's BOM or remove it from this Change.```    |
| 5116  |   |  ```The modified Item is being Recovered and may not contain this Abandoned Item in its BOM. You must Recover it or remove the modified Item from this Change.```    |
| 5117  |   |  ```The modified Item is being Re-Activated and may not contain this Obsolete Item in its BOM. You must Re-Activate it or remove the modified Item from this Change.```    |
| 5118  |   |  ```This Item is in an active phase of the Production stage and cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Production stage Item's BOM or remove it from this Change.```    |
| 5119  |   |  ```The modified Item is being Re-Activated and may not contain this Obsolete Item in its BOM. You must Re-Activate it or remove the modified Item from this Change.```    |
| 5120  |   |  ```Effective Design stage BOMs may not contain Abandoned Items. The effective BOM of this Item contains the Item you are trying to Abandon. In order to Abandon the Item, you must remove it from the working BOM of this Item, and then make the working BOM effective.```    |
| 5121  |   |  ```Effective Production stage BOMs may not contain Obsolete Items. The effective BOM of this Item contains the Item you are trying to Obsolete. In order to Obsolete the Item, you must first remove it from the working BOM of this Item, and then make the working revision effective.```    |
| 5122  |   |  ```Effective Design stage BOMs may not contain Abandoned Items. This Abandoned Item is contained in the BOM of the Item you are trying to Recover. In order to Recover the Item, you must first Recover this Abandoned Item.```    |
| 5123  |   |  ```Effective Production stage BOMs may not contain Obsolete Items. The effective BOM of this Item contains the Item you are trying to Obsolete. In order to Obsolete the Item, you must first remove it from the working BOM of this Item, and then make the working revision effective.```    |
| 5124  |   |  ```Effective Production stage BOMs may not contain Obsolete Items. This Obsolete Item is contained in the BOM of the Item you are trying to Re-Activate. In order to Re-Activate the Item, you must first Re-Activate this Obsolete Item.```    |
| 5125  |   |  ```This Design stage child Item is included in an unapproved Change, and cannot be released to Production as part of this release.```    |
| 5126  |   |  ```This working revision of this assembly contains the Item you are Abandoning and is included in an unapproved Change, so the Item cannot be removed from this assembly.```    |
| 5127  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot removed from this assembly.```    |
| 5128  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot be removed from this assembly.```    |
| 5129  |   |  ```The modified Item is in an active lifecycle phase of the Design stage and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, Recover it, or remove the modified Item from this Change.```    |
| 5130  |   |  ```The modified Item is being released to Production and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from the BOM, release the Design stage Item to Production (by including it in this Change), or remove the modified Item from this Change. If you choose to include the Design stage Item in this Change, you will be taken to the Select Item Modifications page where you can select a Production stage phase for the Item.```    |
| 5131  |   |  ```The modified Item is being released to Production and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from the BOM or remove the modified Item from this Change.```    |
| 5132  |   |  ```The modified Item is being released to Production and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from the BOM, re-activate the child Item, or remove the modified Item from this Change.```    |
| 5133  |   |  ```This Production stage Item cannot contain the Abandoned modified Item in its BOM. You must first remove the modified Item from the Production stage Item's BOM or remove it from this Change.```    |
| 5134  |   |  ```The modified Item is in the Production stage and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from its BOM, re-activate it, or remove the modified Item from this Change.```    |
| 5135  |   |  ```This Item is in the Deprecated phase and cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Deprecated Item's BOM or remove it from this Change.```    |
| 5136  |   |  ```This Item is in an active Design stage and cannot contain in its BOM the Item you are Abandoning. You must first remove it from the Design stage Item's BOM or remove it from this Change.```    |
| 5137  |   |  ```The modified Item is in the Deprecated phase and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from its BOM, Re-Activate it, or remove the modified Item from this Change.```    |
| 5138  |   |  ```This Item is in the Deprecated phase and cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Deprecated Item's BOM or remove it from this Change.```    |
| 5139  |   |  ```This Item is in an active phase of the Production stage and cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Production stage Item's BOM or remove it from this Change.```    |
| 5140  |   |  ```The modified Item is being released to Design and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, recover it, or remove the modified Item from this Change.```    |
| 5141  |   |  ```The modified Item is being released to Production and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from the BOM, release the Design stage Item to Production (by including it in this Change), or remove the modified Item from this Change. If you choose to include the Design stage Item in this Change, you will be taken to the Select Item Modifications page where you can select a Production stage phase for the Item.```    |
| 5142  |   |  ```The modified Item is being released to Production and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from the BOM, re-activate it, or remove the modified Item from this Change.```    |
| 5143  |   |  ```Review and then correct the errors below in order to make this revision effective.```    |
| 5144  |   |  ```Review and then correct the errors below in order to release this Item to Production.```    |
| 5145  |   |  ```Review and then correct the errors below in order to Abandon this Item.```    |
| 5146  |   |  ```Review and then correct the errors below in order to make this revision effective.```    |
| 5147  |   |  ```Review and then correct the errors below in order to Deprecate this Item.```    |
| 5148  |   |  ```Review and then correct the errors below in order to Obsolete this Item.```    |
| 5149  |   |  ```Review and then correct the errors below in order to Recover this Item.```    |
| 5150  |   |  ```Review and then correct the errors below in order to Re-Activate this Item to an active Production stage phase.```    |
| 5151  |   |  ```Review and then correct the errors below in order to Obsolete this Item.```    |
| 5152  |   |  ```Review and then correct the errors below in order to Re-Activate this Item to an active Production stage phase.```    |
| 5153  |   |  ```Review and then correct the errors below in order to release this Item to Design.```    |
| 5154  |   |  ```Cancel```    |
| 5155  |   |  ```Cancel```    |
| 5156  |   |  ```Cancel```    |
| 5157  |   |  ```Cancel```    |
| 5158  |   |  ```Cancel```    |
| 5159  |   |  ```Cancel```    |
| 5160  |   |  ```Cancel```    |
| 5161  |   |  ```Cancel```    |
| 5162  |   |  ```Cancel```    |
| 5163  |   |  ```Cancel```    |
| 5164  |   |  ```Cancel```    |
| 5165  |   |  ```The working revision of this Item cannot be made effective in its current state.```    |
| 5166  |   |  ```This Item cannot be released to Production in its current state.```    |
| 5167  |   |  ```This Item cannot be Abandoned in its current state.```    |
| 5168  |   |  ```This working revision cannot be made effective in its current state.```    |
| 5169  |   |  ```This Item cannot be Deprecated in its current state.```    |
| 5170  |   |  ```This Item cannot be Obsoleted in its current state.```    |
| 5171  |   |  ```This Item cannot be Recovered in its current state.```    |
| 5172  |   |  ```This Item cannot be Recovered in its current state.```    |
| 5173  |   |  ```This Item cannot be Obsoleted in its current state.```    |
| 5174  |   |  ```This Item cannot be Recovered in its current state.```    |
| 5175  |   |  ```This Item cannot be released to Design in its current state.```    |
| 5176  |   |  ```Effective Design stage BOMs may not contain Abandoned Items. The BOM of the working revision you are trying to make effective contains this Abandoned Item. In order to make the revision effective, you must first remove this Item from the working BOM, or Recover this Item.```    |
| 5177  |   |  ```Effective Production stage BOMs may not contain Design stage components. The BOM of the Item you are trying to release to Production contains this Design stage Item. In order to release both the assembly and the component, you must wait until the pending Changes on the component become effective.```    |
| 5178  |   |  ```Effective Production stage BOMs may not contain Obsolete Items. The BOM of the working revision you are trying to make effective contains this Obsolete Item. In order to make the revision effective, you must first remove this Item from the working BOM, or Re-Activate this Item to an active Production stage phase.```    |
| 5179  |   |  ```Effective Deprecated BOMs may not contain Obsolete Items. The effective BOM of this Item contains the Item you are trying to Obsolete. In order to Obsolete the Item, you must first remove it from the working BOM of this Item, and then make the working revision effective.```    |
| 5180  |   |  ```Effective Deprecated BOMs may not contain Obsolete Items. The effective BOM of this Item contains the Item you are trying to Obsolete. In order to Obsolete the Item, you must first remove it from the working BOM of this Item, and then make the working revision effective.```    |
| 5181  |   |  ```Effective Design stage BOMs may not contain Abandoned Items. You must remove this child Item from the BOM of the Item you are releasing, or Recover the child Item to an active Design stage phase.```    |
| 5182  |   |  ```The BOM of one or more item versions on the Change is pointing to the superseded version of a child item.```    |
| 5183  |   |  ```The modified Item is being released to Design and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from the BOM of the modified Item, release it to Design (by including it in this Change), or remove the modified Item from this Change. If you choose to include this Item in this Change, it will be released to the Design stage at the same phase as the modified Item.```    |
| 5184  |   |  ```The modified Item is being released to Design and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from its BOM, recover it to an active phase, or remove the modified Item from this Change.```    |
| 5185  |   |  ```The modified Item is in the Design stage and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from the BOM of the modified Item, release it to Design (by including it in this Change), or remove the modified Item from this Change. If you choose to include this Item in this Change, it will be released to the Design stage at the same phase as the modified Item.```    |
| 5186  |   |  ```The modified Item is being released to Production and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from the BOM or remove the modified Item from this Change.```    |
| 5187  |   |  ```This Deprecated Item cannot contain the Abandoned modified Item in its BOM. You must first remove the modified Item from the Deprecated Item's BOM or remove it from this Change.```    |
| 5188  |   |  ```This Obsolete Item cannot contain the Abandoned modified Item in its BOM. You must first remove the modified Item from the Obsolete Item's BOM or remove it from this Change.```    |
| 5189  |   |  ```The modified Item is Abandoned and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, release it to the Design stage, or remove the modified Item from this Change.```    |
| 5190  |   |  ```The modified Item is in the Production stage and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from its BOM, release the Design stage Item to Production (by including it in this Change), or remove the modified Item from this Change. If you choose to include this Item in this Change, it will be released to the Production stage at the same phase as the modified Item.```    |
| 5191  |   |  ```File number ${param_1} associated to this Item is not the latest edition of the File. Please remove and re-attach the File to the working revision of the Item. Once this is completed, please retry submitting the Change.```    |
| 5201  |   |  ```There are no Items included in this Change. To add Items, switch to the Items view and click Add Items.```    |
| 5202  |   |  ```No approval deadline has been specified for this Change.```    |
| 5211  |   |  ```The Files view for this Item is included in the Change. However, this view contains no modifications to revision-controlled data. ```    |
| 5212  |   |  ```The Costing view for this Item is included in the Change. However, this view contains no modifications to revision-controlled data.```    |
| 5213  |   |  ```The Sourcing view for this Item is included in the Change. However, this view contains no modifications to revision-controlled data.```    |
| 5214  |   |  ```The Bill of Materials view for this Item is included in the Change. However, this view contains no modifications to revision-controlled data.```    |
| 5215  |   |  ```The Specs view for this Item is included in the Change. However, this view contains no modifications to revision-controlled data.```    |
| 5216  |   |  ```This Item already appears on the BOM. If you want to add this Item, consider removing this duplicate BOM Item and updating the Quantity of the existing BOM Item.```    |
| 5217  |   |  ```The working revision of this Item contains ${sub_content} that are not included in any Change. If you wish to make the modifications in those views effective, add the appropriate views to this Change.```    |
| 5218  |   |  ```The working revision of this Item contains ${sub_content} that are not included in any Change. To make the modifications in those views effective, this Item must be included in a Change with the action "Make Working Revision Effective" selected. (The current Change has been set up to perform a different action on the effective revision of the Item.)```    |
| 5219  |   |  ```One or more superseded revisions of the modified Item are named as substitutes for the modified Item in the assembly listed here. If you would like the newly superseded revision of the modified Item to be included in the effective revision of the assembly once this Change is released, you should take the following steps before submitting the Change: Add the current effective revision of the modified Item as a substitute and then add the assembly to this Change (with its Bill of Materials view modifications designated for release).```    |
| 5220  |   |  ```The revision number selected for this Item is also used on another Change. Submitting this Change may result in multiple revisions of the Item with the same revision number.```    |
| 5221  |   |  ```The revision number selected for this Item is already in use by the last approved revision.```    |
| 5222  |   |  ```The revision number selected for this Item is already in use by a superseded revision of this Item with the same item number.```    |
| 5223  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Releasing to Production. Deprecated Items are not recommended for new design.```    |
| 5224  |   |  ```This Deprecated child Item is contained in the BOM of the modified Item. Deprecated Items are not recommended for new design.```    |
| 5225  |   |  ```The modified Item being Deprecated is contained in the BOM of this Production stage Item. Deprecated Items are not recommended for new design.```    |
| 5226  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Re-activating. Deprecated Items are not recommended for new design.```    |
| 5227  |   |  ```The modified Item in the Deprecated phase is contained in the BOM of this In Production Item. Deprecated Items are not recommended for new design.```    |
| 5228  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Re-activating. Deprecated Items are not recommended for new design.```    |
| 5229  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Releasing to Production. Deprecated Items are not recommended for new design.```    |
| 5230  |   |  ```This Deprecated child Item is contained in the BOM of the modified Item. Deprecated Items are not recommended for new design.```    |
| 5231  |   |  ```The modified Item being Deprecated is contained in the BOM of this Design stage Item. Deprecated Items are not recommended for new design.```    |
| 5232  |   |  ```The modified Item being Deprecated is contained in the BOM of this Unreleased Item. Deprecated Items are not recommended for new design.```    |
| 5233  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Recovering. Deprecated Items are not recommended for new design.```    |
| 5234  |   |  ```The modified Item in the Deprecated phase is contained in the BOM of this Design stage Item. Deprecated Items are not recommended for new design.```    |
| 5235  |   |  ```The modified Item in the Deprecated phase is contained in the BOM of this Unreleased Item. Deprecated Items are not recommended for new design.```    |
| 5236  |   |  ```This Deprecated child Item is contained in the BOM of the Item you are Releasing to Design. Deprecated Items are not recommended for new design.```    |
| 5237  |   |  ```The modified Item is in the Obsolete phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5238  |   |  ```The modified Item is being Recovered and may not contain this Obsolete Item in its BOM. You must Re-Activate it or remove the modified Item from this Change.```    |
| 5239  |   |  ```The modified Item is being Recovered and may not contain this Unreleased Item in its BOM. You must release it to Design or remove the modified Item from this Change.```    |
| 5240  |   |  ```This Production stage Item cannot contain in its BOM the Item you are Abandoning. You must first remove it from the Production stage Item's BOM or remove it from this Change.```    |
| 5241  |   |  ```This Item is in the Deprecated phase and cannot contain in its BOM the Item you are Abandoning. You must first remove it from the Deprecated Item's BOM or remove it from this Change.```    |
| 5242  |   |  ```This Item is in the Obsolete phase and cannot contain in its BOM the Item you are Abandoning. You must first remove it from the Obsolete Item's BOM or remove it from this Change.```    |
| 5243  |   |  ```The modified Item is in the Abandoned phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Design, or remove the modified Item from this Change.```    |
| 5244  |   |  ```The modified Item is being Re-Activated and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5245  |   |  ```The modified Item is being Re-Activated and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM or remove the modified Item from this Change.```    |
| 5246  |   |  ```The modified Item is being released to Production and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from the BOM, release it to Production (by including it in this Change), or remove the modified Item from this Change. If you choose to include the Unreleased Item in this Change, you will be taken to the Select Item Modifications page where you can select a Production stage phase for the Item.```    |
| 5247  |   |  ```The modified Item is being released to Production and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from the BOM, recover it and release it to Production, or remove the modified Item from this Change.```    |
| 5248  |   |  ```The modified Item is being released to Design and may not contain this Obsolete Item in its BOM. You must remove the Obsolete Item from its BOM, or remove the modified Item from this Change.```    |
| 5249  |   |  ```The modified Item is in the Obsolete phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5250  |   |  ```This Item is in the Deprecated phase and cannot contain in its BOM the Item you are Obsoleting. You must first remove it from the Deprecated Item's BOM or remove it from this Change.```    |
| 5251  |   |  ```The modified Item is in the Obsolete phase and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, or remove the modified Item from this Change.```    |
| 5252  |   |  ```This Design stage Item either currently appears in the BOM of the Item you are Obsoleting, or contains in its BOM the Item you are Obsoleting. If it is in the Obsolete Item's BOM, you must remove it from the BOM, Release it to Production, or remove the modified Item from this Change. If the In Design Item contains in its BOM the Item you are Obsoleting, you must first remove the Obsolete Item from the In Design Item's BOM or remove it from this Change.```    |
| 5253  |   |  ```The modified Item is being Re-Activated and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM or remove the modified Item from this Change.```    |
| 5254  |   |  ```The modified Item is being Re-Activated and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM or remove the modified Item from this Change.```    |
| 5255  |   |  ```The modified Item is being Re-Activated and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5256  |   |  ```The modified Item is in the Obsolete phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5257  |   |  ```The modified Item is in the Obsolete phase and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, or remove the modified Item from this Change.```    |
| 5258  |   |  ```This Design stage Item either currently appears in the BOM of the Item you are Obsoleting, or contains in its BOM the Item you are Obsoleting. If it is in the Obsolete Item's BOM, you must remove it from the BOM, Release it to Production, or remove the modified Item from this Change. If the Design stage Item contains in its BOM the Item you are Obsoleting, you must first remove the Obsolete Item from the Design stage Item's BOM or remove it from this Change.```    |
| 5259  |   |  ```The modified Item is in the Deprecated phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5260  |   |  ```The modified Item is in the Deprecated phase and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, or remove the modified Item from this Change.```    |
| 5261  |   |  ```The modified Item is in the Deprecated phase and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5262  |   |  ```The modified Item is being Re-Activated and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM or remove the modified Item from this Change.```    |
| 5263  |   |  ```This Unreleased child Item is included in an unapproved Change, and cannot be released to Design.```    |
| 5264  |   |  ```This Unreleased child Item is included in an unapproved Change, and cannot be released to Production.```    |
| 5265  |   |  ```This Unreleased child Item is included in an unapproved Change, and cannot be released to Design.```    |
| 5266  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot be removed from this assembly.```    |
| 5267  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot be removed from this assembly.```    |
| 5268  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot removed from this assembly.```    |
| 5269  |   |  ```This working revision of this assembly contains the Item you are Obsoleting and is included in an unapproved Change. The Item cannot removed from this assembly.```    |
| 5270  |   |  ```This working revision of this assembly contains the Item you are Abandoning and is included in an unapproved Change, so the Item cannot be removed from this assembly.```    |
| 5271  |   |  ```This working revision of this assembly contains the Item you are Abandoning and is included in an unapproved Change, so the Item cannot be removed from this assembly.```    |
| 5280  | 5230  |  ```The modified Item is in the Production stage and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM or remove the modified Item from this Change.```    |
| 5281  | 5231  |  ```The modified Item is in the Production stage and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM or remove the modified Item from this Change.```    |
| 5282  | 5232  |  ```The modified Item is in the Deprecated phase and may not contain this Design stage Item in its BOM. You must remove the Design stage Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5283  | 5233  |  ```The modified Item is in the Deprecated phase and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, or remove the modified Item from this Change.```    |
| 5284  | 5234  |  ```The modified Item is in the Deprecated phase and may not contain this Unreleased Item in its BOM. You must remove the Unreleased Item from its BOM, Release it to Production, or remove the modified Item from this Change.```    |
| 5285  | 5235  |  ```This Design stage Item either currently appears in the BOM of the Item you are Obsoleting, or contains in its BOM the Item you are Obsoleting. If it is in the Obsolete Item's BOM, you must remove it from the BOM, Release it to Production, or remove the modified Item from this Change. If the Design stage Item contains in its BOM the Item you are Obsoleting, you must first remove the Obsolete Item from the Design stage Item's BOM or remove it from this Change.```    |
| 5286  | 5236  |  ```The modified Item is in the Obsolete phase and may not contain this Abandoned Item in its BOM. You must remove the Abandoned Item from its BOM, or remove the modified Item from this Change.```    |

