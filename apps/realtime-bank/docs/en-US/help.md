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
- [Something Wrong/Missing?](fix.md)


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

---

#### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
