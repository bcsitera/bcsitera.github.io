# Expense Reports
Expense Reports solution in BC enables the following:

- Management of expense and travel reports (including approvals and allowances)
- Management of expense documents (with different currencies)
- Digital archive of expense documents
- Connection to digitization partner <a href="https://costpocket.com/en" target="_blank">CostPocket.com</a>  

## Settings
To use the solution, **Expense Reports Setup** must be opened and following fields filled:

|Field|Explanation|
|---|---| 
| Expense Report Nos. | To specify Expense report number series. Value can be chosen from **No. Series List**.|
| Expense Document Nos. | To specify Expense document number series. Value can be chosen from **No. Series List**.|
| Vendor Registration No. Field | Solution uses vendor registration number for automatic detection of Vendor. Since different country localisations use different fields for storing this data, we have made this value selectable by User. **This selection is recommended but NOT mandatory**. Starting from BC version 21.5 the registration no. field has number 25 |
| Default Allowance Account No. field | To specify Default G/L account for posting Daily allowance sum. Value can be chosen from **G/L Accounts list**.|
| Document Attachment Type | Specifies the document attachment type. **Recommended value is Small PDF**. If not specified then CostPocket sends attachment as image.|

All expense documents are posted via journal and User can **select a Journal Template and Batch** for this. During app installation a General journal batch named EXPREP-APP is created.

To use digitization partner **CostPocket** functionality, action **Registration** must be used for one time. User information in CostPocket registration form page is used to determine Primary user, who shall receive e-mail from CostPocket along with instructions how to use CostPocket app. After successful registration connection with CostPocket is established.  

**Job Que Entries** for automatic importing of expense reports/documents can be created with **button "Job Que Entries"** (can be found in More Options -> Actions) . If Job Que entry doesn't exist, then system creates it. Job que entry for expense documents is only needed when documents without report is allowed.  

**For predetermined cost types** User can setup default cost accounts. That can be done in **Cost Types** page. Now when expense documents are imported from CostPocket, system assigns a default G/L cost account determined by document's cost type. **Note!** Default cost account is assigned to cost document **only** when existing Vendor is detected via Registration No. or VAT Registration No.  

For payment method automation User can setup **Payment Method Mapping** so that custom Payment Methods are received from CostPocket and then mapped to BC Payment Method Code. Now when expense documents are imported from CostPocket _(for example using Payment Card Report)_, system assigns **automatically** that **Payment Method**  to cost document.  

**Approval** of an expense report and setting it up is similar to <a href="https://docs.microsoft.com/en-us/dynamics365/business-central/walkthrough-setting-up-and-using-a-purchase-approval-workflow/" target="_blank">Setting Up and Using a Purchase Approval Workflow</a>. On page Workflows use button "New Workflow from Template" and just select **Expense Report Approval Workflow**. After enabling the workflow, User can post an expense report only when it's been approved (status becomes Released).<br>
To notify for example a bookkeeper about a new imported expense report, use workflow template **Expense Report New Entry Notification Workflow**.  

**Solution is ment to be used with logic:**  
User operates daily/weekly in CostPocket app, taking pictures of expense documents and adding them to an Expense report. Bookkeeper operates in BC, receiving expense reports with connected expense documents from CostPocket. Checks postings, sends for approval and posts report with documents.    
*For special cases where Expense reports are not used, User can mark **Allow Documents without Report**, which makes individual document posting possible.*  

## Use
### Expense Reports

**Manual creation** of an expense report is usually done after manual creation of expense documents. User can add documents to report with action **Add documents to Report**.

Expense reports *(with status Report ready)* will be imported from CostPocket, when user presses button **Get Reports from CostPocket** or when job que entry starts *(Object type to run is Report and ID is 24008101)*.  Among with an expense report all expense documents, that are connected to this report, shall also be  imported to BC.   

On Expense report card User can see total sum of expense documents in LCY.  

User can edit submitter information by selecting value from Employees table to **Submitter No.** field. When selecting new value system asks if documents (report lines) should also be updated.  
User must set posting date for report and all connected expense documents by entering value to field **Posting Date**.   

User can change **Sum of Daily Allowance** and Allowance Account No. if needed.

User can open list of connected expense documents when clicking on **Number of Documents** field value.    

**Dimensions** selected to expense report shall be used on all connected documents and document rows (if confirmed by user). Default dimensions attached to submitter employee are also automatically added to all connected documents.    

**Approval** process is similar to <a href="https://docs.microsoft.com/en-US/dynamics365/business-central/across-how-use-approval-workflows/" target="_blank">Use Approval Workflows</a>.    

**Posting** of an expense report means that all connected expense documents are posted along with Sum of daily allowance. *Documents are posted individually.*    

Posted expense reports can be found in **Posted Expense Reports** archive.    

### Expense Documents

Manual creation of expense document is possible and is similar to regular purchase invoice.  

**Vendor and Submitter must be used**.  *When getting documents from CostPocket system looks for Vendor Registration No. and/or VAT Registration No. in order to find Vendor from existing Vendors. Similarly submitter e-mail is used to look for Employee with matching company Email from Employees.*  
User can make multiple document lines with different posting groups (to manage VAT).    

**Dimensions** are applied for document header and lines.  

It's possible to add **Attachments** (different file formats) to expense documents and it's also possible to take picture. There can be many attachments.  
In **Expense Preview** the main attachment is shown (_provided user's internet brauser supports the preview of the attached file type_). To specify the main attachment, open "Attached Documents" page and use action "Set as Main Attachment for Expense".
To view MS Office files as preview a browser plugin <a href="https://chrome.google.com/webstore/detail/office-editing-for-docs-s/gbkeegbaiigmenfmjfclcdgdpimamgkj?hl=en-US" target="_blank">**Office Editing for Docs, Sheets & Slides**</a> 
(_made by Google_) for chromium based browsers (_like Google Chrome and Microsoft Edge_) needs to be installed.  

Expense document's **Billing Type** can be Personal or Company, depending on finances used. If Billing type is Company, then **Payment Method Code** can be used to specify how expense was paid and then debt to vendor is closed according to that Payment method (similar to Purchase invoice).  

Currency exchange rate can be adjusted by **Currency Factor** field.  

User can work with documents on document card or in expense documents list *(mainly to assign Vendor/Submitter/Expense account)*.  
When an expense account is assigned to document header, User shall be prompted, if document lines should also be updated.  
User can check posting with action **Post Preview**.  
Solution will make posting entries to both Vendor ledger entries and Employee ledger entries *(when Submitter has paid for expense document using personal finances).*  

Documents are usually posted from Expense Report. *In special case, when Allow documents without reports selection is used, expense documents can be imported separately with action **Get Documents from CostPocket** and then a document can also be posted from Expense Document list/card.*

Posted expense documents can be found in **Posted Expense Documents** archive.  

To correct or cancel a posted Expense Document or Report, User can use action **Correct**, **Cancel**, **Create Corrective Expense Document/Report**.

---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
