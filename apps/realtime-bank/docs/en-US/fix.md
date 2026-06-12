---
---

# Most Common Fixes

- [Transactions Were Posted in Advance in the _Payment Journal_](#transactions-were-posted-in-advance-in-the-payment-journal)
- [When Opening the _Payment Reconciliation Journal_, a Warning Appeared That Balances Do Not Match](#when-opening-the-payment-reconciliation-journal-a-warning-appeared-that-balances-do-not-match)
- [New Transactions Have Not Arrived/Transactions Are Missing](#new-transactions-have-not-arrivedtransactions-are-missing)
- [Bank Statements Were Imported Incorrectly, Now There Are Duplicate Transactions in the System](#bank-statements-were-imported-incorrectly-now-there-are-duplicate-transactions-in-the-system)
- [Transactions Are in the _Payment Reconciliation Journal_, but They Are Unapplied](#transactions-are-in-the-payment-reconciliation-journal-but-they-are-unapplied)
- [_High_ Transactions Are in the _Payment Reconciliation Journal_, but Automatic Posting Is in Use](#high-transactions-are-in-the-payment-reconciliation-journal-but-automatic-posting-is-in-use)



## Transactions Were Posted in Advance in the _Payment Journal_

Such payment lines close _Vendor Ledger Entries_ but create new _Bank Account Ledger Entries_ that remain open. In order for these to be closed, you must wait until the bank statement arrives in the system. The system will automatically recognize payments that were posted earlier and match them with existing _Bank Account Ledger Entries_.

If a previously posted transaction is matched with a _Bank Account Ledger Entry_ in the _Payment Reconciliation Journal_, then _Bank Account_ is marked in the "Account Type" column. The "Match Confidence" of these transactions is _High_. You can also run "Preview..." for these, and there will be a message that no new entries will be created. After that, you can post the transactions - this only closes the previously created _Bank Account Ledger Entries_.

If you knowingly start posting all payments to vendors in advance, you can disable "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page.

If this was a one-time occurrence, it is worth temporarily disabling "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page. In the _Payment Reconciliation Journal_, find the transactions that were posted in advance, select them, and run "Remove Applications". Then run "Apply Selected...". Now you can post the transactions and then re-enable "Enable Vendor Ledger Entries Matching" on the _Payment Application Settings_ page.

## When Opening the _Payment Reconciliation Journal_, a Warning Appeared That Balances Do Not Match

The warning compares two values: the specific _Bank Account's_ "Balance in Bank" field and the ending balance in the last XML statement. The "Balance in Bank" field is a calculated field in Business Central that adds and subtracts transaction amounts as they are entered into the system. If a transaction has been skipped through the bank connection, this also means that this balance will be calculated incorrectly.

You need to identify from what date the transaction is missing. To do this, you must compare the internet bank and Business Central's _Bank Accounts_ list in parallel.

In the _Bank Accounts_ list, open the _Filter pane_. Then "Filter totals by", select "Date Filter" and set a date there. Open the same date in the internet bank and compare whether "Balance in Bank" and the internet bank's ending balance match. This way you can identify the first day when the balances differed and find the missing transaction(s). Import the missing transaction(s) into the system again according to the following instructions.

## New Transactions Have Not Arrived/Transactions Are Missing

- Check if all RTB _Job Queue Entries_ are working. In order for automation to work in the future, job queues must be restored. In any case, let the consultant know if jobs have failed. Simply restarting the _Job Queue Entry_ may not be enough for automation to start working again. You can also view the content of error messages under the Job Queue Log Entries. 
  - If the bank-named job has stopped working
    - If the error code starts with 5 (500, 503, etc.), it means that the bank is not accepting requests. In most cases, this indicates either issues with their system or maintenance work.
    - It is also possible that the certificate has expired
  - If the "RTB - Process/Apply/Post" job has stopped working
    - The problem occurred after importing messages from the bank, either during processing, application, or posting. The consultant will help clarify the nature of the problem.
  - If job queues are working
    - Check on the _Bank Account_ page transactions whether transactions are missing
    - The consultant will help clarify the nature of the problem.
- Are there new messages on the _Incoming Bank Messages_ page?
  - If you go to the page and immediately see lines with date(s) that are missing from the system, it means that data has been received from the bank but has not been processed.
    - If they are red, there was an error processing the messages, error info is displayed in the info pane - contact the consultant if necessary
    - If the messages are in bold black text, they are unprocessed. For these, run the "Process" action and clear the filter field
  - If new messages from the respective dates are missing or you are not sure if something is missing...
- Load the missing transactions into the system. There are two options for this: the first is longer but works in any case. **If you use the options below, no transactions will be loaded into the system twice, regardless of whether the transactions were already in the system before or not.**
  - Manual payment file import
    - export the missing bank statements as XML in the internet bank
    - open the _Incoming Bank Messages_ page in Business Central
    - "Import from File" action
    - add the XML statement
    - run the "Process" action
    - clear the filter field
    - **OK**
  - Payment file import via Swedbank bank connection
    - page _Swedbank Gateway Setup_ 
    - action "Request Account Statement" 
    - select "Report Type" _Previous Period_
    - mark the period where transactions are (potentially) missing  
       **NB!** if the current day i.e. today's date falls within the period, a service fee of €0.50 applies
    - **OK**
    - action "Get New Bank Messages" 
    - page _Incoming Bank Messages_
    - action "Process" 
    - clear the filter field
    - **OK**
  - Payment file import via SEB bank connection (if missing transactions are within the last 21 days)
    - page _SEB Baltic Gateway Setup_ 
    - action "Get EOD Transactions"
    - mark the date with (potentially) missing transactions  
       **NB!** must be done separately for each date
    - **OK**
    - page _Incoming Bank Messages_ 
    - action "Process" 
    - clear the filter field
    - **OK**
- Now the transactions are in the _Payment Reconciliation Journal_ and their "Match Confidence" is _None_

## Bank Statements Were Imported Incorrectly, Now There Are Duplicate Transactions in the System

Incorrect import means directly into the Payment Reconciliation Journal - this must not be done.

If transactions were posted this way, now the same transactions have also come through _Realtime Bank_ again into the _Payment Reconciliation Journal_ - this means they can no longer be deleted. Definitely notify the consultant and assess the situation together.

One solution is to uninstall the app (while keeping the data), then delete the duplicate transactions from the _Payment Reconciliation Journal_, reinstall the app, and review user permissions.

## Transactions Are in the _Payment Reconciliation Journal_, but They Are Unapplied

Therefore, an error occurred during automatic application of one or more transactions and the transactions were not applied.

- Filter for transactions whose "Match Confidence" is _None_.
- Select these lines
- Run the "Apply Selected..." action

## _High_ Transactions Are in the _Payment Reconciliation Journal_, but Automatic Posting Is in Use

Therefore, an error occurred during automatic posting of one or more transactions and the transactions were not posted. You need to find the transaction(s) that caused the problem, resolve them, and then post manually.