---
---
# Realtime Bank - User Guide
## Table of Contents

- [Setup](#setup)
- [Transmitting Payments](#transmitting-payments)
- [Incoming Bank Messages](#incoming-bank-messages)
- [Processing Bank Account Transactions](#processing-bank-account-transactions)
- [LinkPay User Guide](linkpay.md)

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
Service URL | Enter the address of bank service. <br> Swedbank - https://psd2.api.swedbank.com/partner/v1/sgw/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/  
Authorization/Device Certificate Filename | Import certificate file (pfx/p12 format). Certifcate will be given by bank.
Authorization/Device Certificate Password | Enter certificate password.
Encryption Certificate (for Swedbank) | Certificate can be downloaded here: http://dev.swedbankgateway.net/info#certificates
Agreement Id/Customer Id | Details from the bank agreement.
### Setup Bank Account
Open Bank Account card and choose the connector in the Bank Connector field. If no connector is specified, the transaction information for this bank account will not be pulled into Business Central.

On the Bank Account card, there is a button Set Starting Date for Bank Connector, where you have to set the date of switching to Realtime Bank and the opening balance in the bank on that day.
### Setup Realtime Bank
Open Realtime Bank Setup and assign the number series for the Posted Transaction Nos. field.

In the Application Logic field, select Payment Reconciliation Journal. Other application methods will not be supported and will be removed in the future.

## Transmitting Payments

On the _Payment Journal_ page you can create payments to be sent to the bank. By clicking on the "Transmit to bank..." button under the _Bank_ tab, the report request page opens. Here, it is possible to activate the function _Wait for processing result_. In this case, the system will wait for the first payment status response from the bank. All the payments in the journal will be combined into one Credit Transfer Register and transmitted to the bank.

**Recommendation from Microsoft**: After the transmitting payments to the bank, all lines in the _Payment Journal_ should be deleted. The payments should only be posted in the _Payment Reconciliation Journal_ once the payments have been declared correct by the bank.

You can find the exported payment files on the same page using the button, or by searching the view, _Credit Transfer Registers_. Under the field _No. of Transfers_, all the transactions of the journal are recorded separately, as well as the payment status for each transaction.

If the user's role is _Accountant_, they will have a _Real-time bank_ cue in the Role Center. Information regarding rejected and pending payments will be displayed there. On the _Rejected Payments_ page, each payment can be individually marked as hidden using the "Hide/Unhide" button - this will remove the problematic payment from the Role Center overview.

## Incoming Bank Messages

### Get bank messages automatically

To get bank messages press the button Get New Bank Messages or setup Job Queue Entries on the bank connector setup page. The process imports new bank statements to the page Incoming Bank Messages. This page is opened with filters: Source and Status.

Clicking on the "Job Queue Entries" button opens the Job Queue Entries page, where you can configure two automatic jobs:
 - retrieving bank messages from the bank, and
 - processing bank messages (incl. applying and posting transactions).

By default, messages that have not yet been processed are displayed. Use the “Show all Messages” to see all entries.

### Import bank statement manually

You can manually import the bank statement file on the _Incoming Bank Messages_ page by clicking the _Import From File_ button. The entry is in the _Received_ status.

### Processing bank messages

To process the file click _Process_ button.  
Then click "Show All Messages" and choose the line.  
You see the status – Processed and No. of Saved Transactions.  
By pressing this number it is possible to go to the Bank Account Transactions.

## Processing Bank Account Transactions

### Bank Account Transactions

In Bank Account card there is a new field Balance in Bank. Drilldown in this field to open Bank Account Transactions. By default you can see unposted transactions which need to be applied before they can be posted.

The number of rejected payments is displayed in the _Realtime Bank_ cue in the Role Center. When the page is opened, it is possible to mark each payment as hidden using the button Hide/Unhide, which removes the payment from the overview.

### Applying Service Fees

You can use Text-To-Account functionality.  

### Applying Invoices
Appying can be done either manually or automatically.

For manual application, assign Applied Account No. and click Apply Manually. This will open the list of open ledger entries. Apply entries by clicking Process->Set Applies-to ID.

For automatic application run the action Apply Automatically.

### Posting

Applied transaction can be posted to ledger entries by clicking Post action.

In addition Job Queue Entry can be configured, which posts transactions automatically when transaction has been applied and Application Status (quality) is 'High Confidence'.

---

### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
