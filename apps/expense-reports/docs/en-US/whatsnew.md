---
---
##### Version 20.0.24144.0
- Fixed issue that prevented importing Expense Reports with daily allowance from CostPocket.  

##### Version 20.0.24134.0
- Improved preview of documents embedded in the solution (including large preview).
  - In addition, you can now choose the format of the attachments received from CostPocket (either PDF or Image).
- Added payment method support for expense documents.  

##### Version 20.0.24107.0
- Added the ability to cancel/correct from the button of the posted expense report and expense documents  

##### Version 20.0.24091.0
- The logic of posting for the expense report has been improved, so that if the Vendor card has a VAT business posting group filled in, it is used in posting.
  - Previously, the “VAT business posting group” was always taken from the “Gen. Business Posting Groups” field “Def. VAT Bus. Posting Group” during posting
- Minor technical additions  

##### Version 20.0.23103.0
- Made the solution compatible with BC22 version
- Added logic when determining the daily allowance account, that dimensions are created for the expense report based on both the employee and the G/L account default dimensions
- Fixed an error situation that occurred when manually creating an expense report (_the system mistakenly went to look for the submitter of the expense report immediately_)
- UX enhancements  

##### Version 15.6.23045.0
- Added fields Country Code (visible) and Country Name (hidden by default) to Expense Report, in order to show country visited on travel report
- Added field Daily allowance entry description (hidden by default) to Expense Report, in order to makedaily allowance G/L entry description editable to user
- Fixed issue, that when changing amounts on expense document lines, then expense document amount on document header did not change immediately (user doesnt have to press F5 anymore)
- Fixed issue, that when expense document had expense type specified but no vendor, then after adding vendor user had to manually remove and reenter cost type in order for the predetermined G/L account to activate  

##### Version 15.6.22178.0
- Fixed situation where it was not possible to add attachments to Expense reports/documents
- Fixed error "The Workflow Event does not exist" that came when reports were imported from CostPocket

##### Version 15.6.22143.1
- It's now possible to add dimensions to expense document lines

##### Version 15.3.22091.0
- Fixed situation where it was possible to post expense report from expense report list without approving although approval workflow was enabled
- Smaller bugfixes and UX improvements

##### Version 15.3.22031.0
- Instead of fixed cost types now there are tree structured editable Expense types that can be synced with CostPocket
- Now You can prepare Expense Report in BC and send it to CostPocket (for adding digitized documents)
- Now You can take pictures of expense documents directly from BC
- Integration between BC and CostPocket now works with status flags - when getting reports and also marking received reports
- Now You can start creation of expense document directly from expense report
- Better prefiltering of G/L account selection
- Travel report fields (Start date and End date and Allowance) now appear only on reports with type Travel
- Fixed situation when adding documents from report didn't make connection between document line and report
- Smaller UX imporvements
