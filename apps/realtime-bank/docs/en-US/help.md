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

## Transmitting Payments

On the _Payment Journal_ page you can create payments to be sent to the bank. By clicking on the "Transmit to bank..." button under the _Bank_ tab, the report request page opens. Here, it is possible to activate the function _Wait for processing result_. In this case, the system will wait for the first payment status response from the bank. All the payments in the journal will be combined into one Credit Transfer Register and transmitted to the bank unsigned, i.e. they are saved as pending payments.

It is also possible to sign the transaction in Business Central before transmission, therefore these payments do not need to be approved in the bank. Certain setups mentioned **[here](#setup-signed-payments)** are necessary before this function can be used. In order to send payments in signed form, the _Sign payments_ function must be toggled on in the pop up window. If the user transmitting the payments is also the required approver for said bank account, the signing process is activated immediately. Other required signees will receive an approval request via email.

Once the transmission of signed payments has been initiated, it is possible to monitor the status of signatures under _Credit Transfer Registers_. To do this, the correct payment file must be selected and the “Signers“ field allows viewing of the required signers on a given payment. It is also possible to see which of the required approvers have already signed and when, as well as information on the email notifications sent. On the same page, it is possible to resend email notifications to users whose signatures are still missing.

If the required approvers are set up for bank accounts, it is still possible to send payments without a signature. To do this, you must disable the _Sign payments_ function. The approvers must then log in to the internet bank and approve the pending payments there – there, all signing methods can be used.

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

You can use Text-To-Account functionality. You can use * in the "Mapping Text" field to make text recognition more universal. You can also assign dimensions to rows using the "Dimensions" function. In addition, you can apply transactions to specific Bank Accounts e.g. if you have set up payment terminals as Bank Accounts in BC.

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
