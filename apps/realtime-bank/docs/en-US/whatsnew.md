---
---

##### Version 24.0.25316.0
- In case of a mass payment (e.g. salary payment), if it is imported from the bank, the data referring to the employee is deleted during processing
- If the ending balance on the bank statement does not match the balance calculated in BC, BC will notify the user in the _Payment Reconciliation Journal_ - this situation may occur if the bank's services are down and not all transactions have been imported
- If the transaction is not applied to any open entry in the _Payment Reconciliation Journal_ and the _Match Confidence_ remains "None", a follow-up action is triggered, which assigns the _Customer/Vendor_ to the transaction based on the Registry code specified for the related party
- If the transaction is applied to a document in the _Payment Matching Journal_ that was previously assigned _Dimensions_, the same _Dimensions_ will also be assigned to the transaction
- When requesting Swedbank Bank Account Statements, it is now possible to request "Yesterday" in addition to "Today" and "Previous Period". You can set it to run automatically every morning - e.g. Citadele, Urbo and Šiauliai (Artea) bank statements are not automatically generated for the previous day.
- The transaction now also displays the "External Document No." in the _Payment Reconciliation Journal_. Previously, it was more difficult to check the validity of purchase invoices paid to vendors, as the "Vendor Invoice No." was indicated in the transaction description, but the _Payment Reconciliation Journal_ only displayed information about related entries using BC's internal document numbers.
- Two bugs have been fixed:
    - When transferring payments, it is possible to wait for the initial processing result to see if the payment was correct and recorded by the bank. In certain cases, an error occurred when displaying the feedback in the pop-up window, which no longer occurs.
    - When using the setting "Match Credit Transfer Register", an error occurred when appling open entries, which has been resolved. 

##### Version 24.0.25248.0
- Added functionality of transmitting payments to banks in signed form using Smart-ID.
- It is possible to enable automatic application of opposite entries in the reconciliation journal, i.e. the system also matches transactions to opposite entries, such as both invoices and credit invoices.
- It is possible to enable application logic, which matches transactions in the reconciliation journal with documents based on data stored in credit transfer registers.
- BC27 compatibility (2025 wave 2)

##### Version 21.0.25143.0

- Job Queue automation only applies new incoming transactions and does not modify existing rows in the Payment Reconciliation Journal.
- Added possibility of automatically applying only selected rows in the Payment Reconciliation Journal.

##### Version 21.0.25024.0

- Added an overview of rejected payments in the role centre and specific feedback on the failures encountered for each rejected payment.
- Added action “Set Starting Date for Bank Connector” to the bank account card. This is used to specify the specific date on which the solution will be activated.

##### Version 21.0.24352.0

- Swedbank Gateway new API is supported.
- [LinkPay](linkpay.md) payment link functionality is now available.

##### Version 21.0.24242.0

- Immediately returns first status of payment file processing results to the user when sending payments to the bank (Swedbank, LHV, Coop).

##### Version 21.0.24105.0

- Coop Bank Gateway is now also available for BC cloud clients.

##### Version 21.0.24085.0

- Luminor Bank AS connection is now supported (Luminor WebService).

##### Version 21.0.24017.0

- Added Swedbank Current Day Account Statement query. This is good to use when the amount of transactions is large and a online notifications/alerts are not practical.

##### Version 21.0.24017.0

- Coop Pank Gateway is now supported
- Only messages regarding bank accounts that are configured in BC are imported. Necessary if there are bank accounts for which transaction information is not desired in BC.

##### Version 21.0.23153.1

In the RTB Payment Reconciliation Journal, it is now possible to split a single bank transaction line into multiple lines using the “Transfer difference to account” button. Posting checks that the sum of the split rows matches the amount of the bank transaction.

##### Version 21.2.23145.0

The “Payment Reconciliation Journal” can now be used for applying and posting of bank transactions.

In this case, bank transactions are imported into the RTB named Payment Reconciliation Journal”. This is a permanent journal, which is not deleted on posting and from which partial posting is also allowed. On Journal Line posting, the transaction is marked as posted in the bank transactions window.

The use of the Payment Reconciliation Journal needs to be activated in the ‘Application Logic’ filed of “Realtime Bank Setup”. Other application methods will not be supported and will be removed in the future. 

##### Version 20.2.23046.0

- Added the possibility to set default dimensions for text to account matching.
- Bugfix: the account description entered by the user was sometimes not included with posting.

##### Version 20.2.23035.0

- Added direct transfer of payments to Swedbank (in addition to LHV, SEB).

##### Version 20.2.23015.0

- Added event OnBeforeMatchBankPayments, which can be used to replace the application code block 1255 “Match Bank Payments” with its own version.

##### Version 20.2.23014.0

- Application improvements:
    - In the case of manual application, the Bank Account Ledger Entries did not close.
    - No posting entries were generated when matching was changed to standard application  

##### Version 20.2.22358.0

- With the “Transmit to bank” action, payments can now also be forwarded to SEB bank.
- The “Get EOD Transactions” action has been added to the SEB Baltic Gateway Setup page, which allows requesting of completed bank day statements (up to 20 days back). This functionality is useful in case the intraday loading was incomplete or stopped for some reason. In this case, missing transactions can be retrieved from the statement of the previous banking days.
- A “Cust. Ref. No. Field No.” has been added to the Realtime Bank Setup page. The setting helps to identify the customer in case there are no linked invoices. Previously, identification was already based on the registration number and IBAN.

##### Version 20.2.22351.0

- The “Transmit to Bank” action has been added to the Payment Journal, allowing payments to be forwarded directly to LHV.

##### Version 20.2.22189.0

- The application logic based on the Payment Application Rules has been improved:
    - The Match Confidence indicator Medium has been added, since the Payment Application Rules use it.
    - Map Text to Account supports filter form inputs (e.g. @bank service*).
    - Application also reapplies already applied entries if they have not been manually applied.  


- The option to set default dimensions has been added to the Map Text to Account feature.

##### Version 16.0.22179.0

- In addition to the existing built-in application logic, it is now possible to use a standard-based application logic (based on Payment Application Rules). The choice can be made in the Realtime Bank Setup. The logic is exactly the same as in the standard, but if the standard does not find an invoice, the additional logic will find the other party via registration number or IBAN.

##### Version 16.0.22157.0

- All three banks are now supported in the cloud version: Swedbank, SEB and LHV.