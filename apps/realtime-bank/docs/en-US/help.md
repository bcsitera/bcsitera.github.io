---
---

# Realtime Bank: User Guide

## Table of Contents

- [Setup](#setup)
- [Role Center](#role-center)
  - [Realtime Bank Cue](#realtime-bank-cue)
- [Payment Journal Page](#payment-journal-page)
  - [Transmitting Payments to the Bank](#transmitting-payments-to-the-bank)
- [Bank Accounts Page](#bank-accounts-page)
- [Payment Reconciliation Journals Page](#payment-reconciliation-journals-page)
- [Something Wrong/Missing?](#something-wrongmissing)

## Setup

### Setup Bank Connetors

The following connectors are supported out-of-the-box:
1. Swedbank Gateway
2. SEB Baltic Gateway
3. LHV Connect
4. Coop Pank Gateway
5. Luminor Web Service

Instructions to join with the service can be found [here](join.md).

Each has its own setup card. Please open the setup of your bank connector and enter the following information: 

Field |  Description | 
-- | --
Service URL | Enter the address of bank service. <br> Swedbank - https://psd2.api.swedbank.com/partner/v1/sgw/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/ <br> Luminor - https://ftc.luminoropenbanking.com/v1/ft-services/CorporateFileService  
Authorization/Device Certificate Filename | Import certificate file (pfx/p12 format). Certifcate will be given by bank.
Authorization/Device Certificate Password | Enter certificate password.
Agreement Id/Customer Id | Details from the bank agreement.


### Setup Bank Account
Open Bank Account card and choose the connector in the Bank Connector field. If no connector is specified, the transaction information for this bank account will not be pulled into Business Central.

On the Bank Account card, there is a button Set Starting Date for Bank Connector, where you have to set the date of switching to Realtime Bank and the opening balance in the bank on that day.

### Setup Realtime Bank
Open Realtime Bank Setup and assign the number series for the Posted Transaction Nos. field. If there are bank accounts that you do not want to be reflected in Business Central, it is possible to download only bank messages that relate to the accounts saved in Business Central. To do this, enable the feature "Filter Incoming Messages". "Clear Incoming Sensitive Content" deletes sensitive data such as employees' personal details if the imported bank message contains consolidated payments.

In the settings related to the processing of bank messages, it is possible to display service fees on separate lines in the _Payment Reconciliation Journal_. To do this, enable "Charges on Separate Line". If you enable "Name in Posting Description", the name of the related party will also be added to the text of the transaction taken from the bank.

In the _Application Logic_ field, select "Payment Reconciliation Journal". Other application methods will soon not be supported and will be removed. 

"Match Opposite Entries" means that when applying, the system also searches for matching entries among open entries with opposite symbols. E.g. both invoice and credit invoice entries are used. If the payment was made via Business Central, "Match Credit Transfer Register" automatically matches the transactions with the data from the Credit Transfer Registers. If "Match Customer/Vendor" is on and the transaction is not applied to any open entry, then the transaction is applied to the Client/Vendor account based on the registration code.

"Dimensions from Applied Entry" - if the transaction is linked to an open entry to which dimensions have been previously assigned, then the same dimensions are applied to the transaction. "Dimensions from Text-to-Account" allows you to add dimensions within the functionality.

### Setup Signed Payments

In order to send signed payments, the required approvers must be set up in Business Central. There may be one or more approvers. The required approvers can be assigned to a bank account both in the _Bank Accounts_ list and separately on each _Bank Account_ card. All assigned users are mandatory for the transmission of the payment - if even one approver signature is missing, the payment will not be transmitted to the bank. 

All users who are assigned as approvers must also be set up as _Smart-ID users_ - refer to our **[Smart-ID User Guide](../../../smart-id/docs/en-US/help.md)**. In Business Central, it is only possible to sign via Smart-ID – other signing solutions are not supported in Business Central. Email notifications with approval request will be sent to the persons' email address listed under “Contact Email“ on the _User_ card.

## Role Center

### _Realtime Bank_ Cue  

#### Rejected Payments

Information about rejected payments appears here. If the bank detected an error after the payment was sent from the _Payment Journal_ to the bank, the transaction will appear here. Each transaction has a description of what the error was. At the top there is an action "Hide/Unhide", which can be used to remove transactions from this cue.

#### Pending Payments

Information about payments that have been transmitted to the bank and are on the pending payments list appears here. These must be approved in the bank.

## _Payment Journal_ Page

Payment lines must be created here. You can also make payments for the future - the transfer will take place on the date marked as "Posting Date".

### Transmitting Payments to the Bank

Without the _Realtime Bank_ app, you must click "Export..." on the _Bank_ tab - an XML file will be created, which must be imported in the internet bank. With the Realtime Bank app, you must click "Transmit to bank...". 

#### Wait for Processing Result

If "Wait for processing result" is enabled, payment processing occurs immediately and you receive the first feedback on whether all transactions were correct. If the feedback says "Accepted", all lines were correct.

If the feedback says "Rejected", the entire payment file was rejected. If the feedback says "Partially accepted", then at least one payment line in the file was problematic.

To see what the problem is, you must click "Credit Transfer Registers" on the _Bank_ tab in the same _Payment Journal_. The top line is the payment file that was just exported, and by clicking on the "No. of Transfers" field, a detailed view opens with all transactions. The lines that were problematic and did not pass the bank's verification and were not saved to the bank are also marked there.

#### Unsigned Payments

If "Sign payments" is off - unsigned payments are sent to the bank and must be approved in the bank. In the bank, all options can be used for signing - ID card, Smart-ID and Mobile-ID.

#### Signed Payments

If "Sign payments" is on - an XML is created in the background, which awaits Smart-ID signatures from authorized persons. To use the solution, the Smart-ID app must be installed, users' personal identification codes must be configured, and authorized persons must be assigned to bank accounts.

**If the creator of the payment lines is also an authorized approver:**

A Smart-ID signing window will open immediately for them and they can sign immediately.

**If there are other authorized approvers/the creator of the payment lines is not an authorized approver:**

The system sends an email to the approver(s). The email contains a link that points to the Business Central page _Credit Transfer Reg. Entries_ where all transactions that go to the bank as one payment file are displayed. In Business Central, the transactions can be reviewed and then signed with Smart-ID. To do this, there is an action at the top "Sign All".

**Where to find transactions requiring signing in Business Central?**

All payment files are located on the _Credit Transfer Registers_ page. You can get there by going to the _Payment Journal_ and the _Bank_ tab. You can also find the page by entering it in the search.

Payment files awaiting signing have _Signing in Progress_ written in the "Signature Status" field. If you open the "Signers" field, all required signers are displayed there, as well as whether they have already signed and when. Email notifications can also be resent from there.

To see all the transactions in the payment file and review them before signing, you must open the "No. of Transfers" field. Using the "Sign All" action, you can approve the lines with Smart-ID.

**When does the payment move to the bank?**

As soon as all authorized persons have confirmed the payment file with their signature, the payment file moves to the bank. In the _Credit Transfer Registers_, the "Signature Status" field also shows _Sent_. There is no longer any need to approve anything in the internet bank, and the transactions will wait for their transfer date.

#### Payments Transmitted to the Bank

We recommend posting transactions only after they have been imported later with a bank statement. This way, there is certainty that the transaction actually went through at the bank. If you still need to post in advance or did so by mistake - you will find the answer below.

The _Payment Journal_ must be cleared after sending payments to the bank. All open entries are already applied to payments on this journal worksheet - when importing a bank statement, connections with the same entries will not be recognized. The _Payment Journal_ must be cleared.

## _Bank Accounts_ Page

All bank accounts have new fields: "Balance in Bank" and "Amount not Posted". If the bank account is configured through a Gateway connection, clicking on the amounts in the fields will open more detailed views.

### Balance in Bank

The "Balance in Bank" value displays the actual balance in the internet bank. This is recalculated with each transaction and is as current as the newest message received through the bank connection.

By clicking on the amount in the "Balance in Bank" field, all transactions for that bank account open in a one-to-one format, exactly as they are in the internet bank. Outgoing transactions are in red, incoming transactions are in green. A log is also saved here - whether the transaction has been posted to the general ledger or not, what the "Match Confidence" was at the time of posting. If automatic posting is used, then for transactions posted automatically, the "Match Confidence" is marked as _High_.

### Amount not Posted

The "Amount not Posted" field is the difference between the "Balance in Bank" and "Balance" (i.e., the amount posted to the general ledger) fields.

Clicking on the "Amount not Posted" field opens the _Payment Reconciliation Journal_ for that bank account. Here you will find transactions for that bank account that have been received through the _Realtime Bank_ connection and still require review by the accountant before posting. The same transactions can be accessed by searching for _Payment Reconciliation Journals_.

### _Bank Account_ Card

Here you can assign required signers to the bank account to use signed payment transmission. All users who are assigned as required signers must confirm the payment file with their signature for it to go to the bank. Users can be assigned using the "Signers" action.

## _Payment Reconciliation Journals_ Page

This is a list of bank accounts that have so far used the _Realtime Bank_ connection to import transactions. By opening them, you can review transactions that are not yet posted to the general ledger. Lines cannot be deleted here.

All transactions regardless of date are in one view. It is possible to filter them by date. It is also not possible to delete transactions. In order to post a transaction, you must make sure that there are no red amounts in the "Difference" column. This means that it is money that has remained unapplied and must be applied before posting.

**How to move a red "Difference" amount to a separate line?**

Make the row whose "Difference" you want to move to a new line active. Go to the "Manual Application" tab and select "Transfer Difference to Account" there. Choose either _Customer_, _Vendor_ or _G/L account_ and click OK.

If the created line needs to be applied to a specific _Customer_/_Vendor_ open entry, make the added line active and click "Remove Applications". Now open the manual application window - either click on the value in the "Match Confidence" cell or go to the _Manual Application_ tab and select "Apply Manually..." there. Now you can select the specific open entry to apply the transaction with.

"Difference" can be transferred to new lines as many times as necessary.

**Accepting Applications**

Transactions that have been reviewed should be marked - use the "Accept Applications" action for this. This makes it easier to manage which transactions have been checked and accepted. This is also helpful if you want to visually reduce transactions in the journal and partially post them.

**How to partially post?**

If you are ready to post some transactions, click the "Post..." button. A pop-up window will now open. The same filters that were in the journal worksheet view are automatically filled in. In addition, you can mark what "Match Confidence" must be present to post the transactions. If the filter fields are left empty, all transactions in the view will be posted.

You can also select filters in the posting preview in the same way.

**Text-to-Account Mapping**

Here you can define parts of the transaction text and which account the system should automatically apply them to. For example, transactions containing the text "service fee" can be assigned to specific _G/L accounts_.

Additions. In the "Mapping Text" field, you can use *, to define the transaction mapping text even more precisely. In addition to G/L accounts, transactions can also be assigned to specific _Customer_, _Vendor_ or _Bank Account_ accounts (e.g., card terminals).

You can also assign _Dimensions_ to each line. To do this, use the "Dimensions" action. You can add one or more dimensions there and assign specific _Dimension Values_.

A "Mapping Related-Party Type" field has also been added, where you can specify whether the mapping is triggered only for _Organizations_ or only for _Private Persons_. If the field is left empty, the mapping is triggered regardless of the payer type.

## Something Wrong/Missing?

### Transactions Were Posted in Advance in the _Payment Journal_

Such payment lines close _Vendor Ledger Entries_ but create new _Bank Account Ledger Entries_ that remain open. In order for these to be closed, you must wait until the bank statement arrives in the system. The system will automatically recognize payments that were posted earlier and match them with existing _Bank Account Ledger Entries_.

If a previously posted transaction is matched with a _Bank Account Ledger Entry_ in the _Payment Reconciliation Journal_, then _Bank Account_ is marked in the "Account Type" column. The "Match Confidence" of these transactions is _High_. You can also run "Preview..." for these, and there will be a message that no new entries will be created. After that, you can post the transactions - this only closes the previously created _Bank Account Ledger Entries_.

If you knowingly start posting all payments to vendors in advance, you can disable "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page.

If this was a one-time occurrence, it is worth temporarily disabling "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page. In the _Payment Reconciliation Journal_, find the transactions that were posted in advance, select them, and run "Remove Applications". Then run "Apply Selected...". Now you can post the transactions and then re-enable "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page.

### When Opening the _Payment Reconciliation Journal_, a Warning Appeared That Balances Do Not Match

The warning compares two values: the specific _Bank Account's_ "Balance in Bank" field and the ending balance in the last XML statement. The "Balance in Bank" field is a calculated field in Business Central that adds and subtracts transaction amounts as they are entered into the system. If a transaction has been skipped through the bank connection, this also means that this balance will be calculated incorrectly.

You need to identify from what date the transaction is missing. To do this, you must compare the internet bank and Business Central's _Bank Accounts_ list in parallel.

In the _Bank Accounts_ list, open the _Filter pane_. Then "Filter totals by", select "Date Filter" and set a date there. Open the same date in the internet bank and compare whether "Balance in Bank" and the internet bank's ending balance match. This way you can identify the first day when the balances differed and find the missing transaction(s). Import the missing transaction(s) into the system again according to the following instructions.

### New Transactions Have Not Arrived/Transactions Are Missing

- Check if all RTB _Job Queue Entries_ are working. In order for automation to work in the future, job queues must be restored. In any case, let the consultant know if jobs have failed. Simply restarting the _Job Queue Entry_ may not be enough for automation to start working again.
  - if the bank-named job has stopped working
    - most likely the service was down at the bank, the connection was lost, and the job queue could not be automatically restored by the system
    - it is also possible that the certificate has expired
    - other problem
  - if the "RTB - Process/Apply/Post" job  has stopped working
    - the consultant will clarify the nature of the problem
  - if job queues are working
    - check on the _Bank Account_ page transactions whether transactions are really missing
    - notify the consultant
- Are there new messages on the _Incoming Bank Messages_ page?
  - if you go to the page and immediately see lines with date(s) that are missing from the system, it means that data has been received from the bank but has not been processed.
    - if they are red, there was an error processing the messages, error info is displayed in the info pane - contact the consultant if necessary
    - if the messages are in bold black text, they are unprocessed. for these, run the "Process" action and clear the filter field
  - if new messages from the respective dates are missing or you are not sure if something is missing...
- Load the missing transactions into the system. There are two options for this: the first is longer but works in any case. **If you use the options below, no transactions will be loaded into the system twice, regardless of whether the transactions were already in the system before or not.**
  - Manual payment file import
    - export the missing bank statements as XML in the internet bank
    - open the _Incoming Bank Messages_ page in Business Central
    - there is an "Import from File" action there
    - add the XML statement there
    - run the "Process" action on the new message(s)
    - clear the filter field
    - **OK**
  - Payment file import via Swedbank bank connection
    - on the _Swedbank Gateway Setup_ page
    - "Request Account Statement" action
    - select "Report Type" Previous Period
    - mark the period where transactions are (potentially) missing  
       **NB!** if the current day i.e. today's date falls within the period, a service fee of €0.50 applies
    - **OK**
    - run the "Get New Bank Messages" action
    - on the _Incoming Bank Messages_ page
    - run the "Process" action
    - clear the filter field
    - **OK**
  - Payment file import via SEB bank connection (if missing transactions are within the last 21 days)
    - on the _SEB Baltic Gateway Setup_ page
    - "Get EOD Transactions" action
    - mark the date with (potentially) missing transactions  
       **NB!** must be done separately for each date
    - **OK**
    - on the _Incoming Bank Messages_ page
    - run the "Process" action
    - clear the filter field
    - **OK**
- Now the transactions are in the _Payment Reconciliation Journal_ and their "Match Confidence" is _None_

### Bank Statements Were Imported Incorrectly, Now There Are Duplicate Transactions in the System

Incorrect import means directly into the Payment Reconciliation Journal - this must not be done.

If transactions were posted this way, now the same transactions have also come through _Realtime Bank_ again into the _Payment Reconciliation Journal_ - this means they can no longer be deleted. Definitely notify the consultant and assess the situation together.

As a solution, you can try whether the system allows posting these transactions to an intermediate account, e.g., _Cash in Transit_. Then make manual reversing entries to reverse them.

If the system does not allow this, then you must:

- write down which users currently have the _Realtime Bank_ permission sets BGW REALTIMEBANKFULL and BGW REALTIMEBANKLITE in use
- uninstall the Realtime Bank app (**do not** delete data)
- delete the transactions in the _Payment Reconciliation Journal_
- install the app again
- restore the _Realtime Bank_ permission sets BGW REALTIMEBANKFULL and BGW REALTIMEBANKLITE for users

### Transactions Are in the _Payment Reconciliation Journal_, but They Are Unapplied

Therefore, an error occurred during automatic application of one or more transactions and the transactions were not applied.

- Filter for transactions whose "Match Confidence" is _None_.
- Select these lines
- Run the "Apply Selected..." action

### _High_ Transactions Are in the _Payment Reconciliation Journal_, but Automatic Posting Is in Use

Therefore, an error occurred during automatic posting of one or more transactions and the transactions were not posted. You need to find the transaction(s) that caused the problem, resolve them, and then post manually.

---

#### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
