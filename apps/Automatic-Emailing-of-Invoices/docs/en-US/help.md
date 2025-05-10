# Automatic Emailing of Invoices
Automatic Emailing of Invoices solution in Business Central enables the following: 
- Specify through Document sending profile to send invoices automatically by email
- Overview of sending status and time sent on posted invoices list
- Manage the number of invoices sent with a single job que run (to avoid email server blacklisting)
- Send invoice to Bill-to Customer or Sell-to Customer (or to Both) email address


### Prerequisites and setup:
- For successful Sales invoice and Credit Memo sending by email "Use for Email Attachment" must be selected in "Report Selection - Sales" page (Usage Invoice or Credit Memo respectably).
  - Solution will notify this to user if needed when selection "Send invoice by Email automatically" is activated on Document sending profile.
- Job queues are needed to send invoices with status "Waits for Sending"
  - Solution will create job queues needed when selection "Send invoice by Email automatically" is activated on Document sending profile and will notify user about the Specify Max No. of Inv. Sent with One Job.
<br>
  
**Job queue mentionable settings:**
  
|Field|Explanation|
|---|---|
|Object Type to Run|Report|
|Object ID to Run|70405500 for Sales invoices and 70405501 for Credit Memos|
|Report Request Page|Specify Max No. of Inv. Sent with One Job.<br>By default 100 invoices are sent with a single job queue run.<br>This setting should correspond to Your email server limits (ask from Your IT administrator) and generally known email spam filter thresholds.<br>This setting also depends on "No. of Minutes between Runs" value set. |

<br>
  
### Usage scenarios:
- **Send invoice automatically to customer by email after posting**
  - Create document sending profile and select "Send invoice by Email automatically". Also if needed specify there "Email Address Source" (default and recommended value is "Bill-To E-Mail").
  - Add document sending profile created to customer card.
  - Specify Email on customer card or "Send To Email" on customer Document Layouts page.
    - It's also recommended to create suitable "Email Body Layout Description" and select "Use for Email Body".
  - After posting the invoice it's marked as "Waits for Sending".
  - Job queue "Send Posted Sales Invoices by E-mail" runs and sends the invoice marking invoice "Email Sent Status" to Sent and filling "Email Sent Time".
- **Send invoice manually by email**
  - Sending invoices manually with action "Send by Email" also marks "Email Sent Status" to Sent and fills "Email Sent Time".
  - Recipient email address is taken according to "Document sending profile" field "Email Address Source".
- **Change "Email Sent Status" manually**
  -  Select posted Sales Invoice/Credit Memo and select Process -> Update Document.
  -  In section "Email Sending" select new value for "Email Sent Status".
    - Note that changing of status clears field "Email Sent Time".
- **View sent email recipient address or cause of error**
  - Select posted Sales Invoice/Credit Memo and select Actions -> Activity log.
<br>
  
#### Notes:
- When emails are successfully handed to email server (_specified through email account used_) then they are marked as successfully sent.
  - Meaning if email server fails to deliver email to recipient then this information does not make it back to Business Central.
    - Solution is to check emails for the account used for sending email on email server.
- When Business Central is unable to hand emails over to email server then status is set to error and these emails can be found in "Failed Emails in Outbox".
  - In case recipient address is missing then status is set to error and email is not attempted to hand over to email server.
    - To check cause of error User should select Actions -> Activity log.


  
  
---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
