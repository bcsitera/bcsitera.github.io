
# Joining

## Table of Contents

- [Submitting the application](#submitting-the-application)
- [Direct Channel vs. Operator Channel](#direct-channel-vs-operator-channel)
- [Supported services](#supported-services)
- [Certificates](#certificates)
- [Setup](#setup)

## Submitting the application

Our Business Central product uses both direct and operator channels for integration — this varies by bank. To join, contact your customer manager or submit an application on the bank's website.

Bank connectors are supported by the following bank providers:

1. [Swedbank Gateway - direct and operator channel](https://www.swedbank.ee/business/d2d/ebanking/gateway)
2. [LHV Connect - direct channel](https://www.lhv.ee/en/connect)
3. [SEB Baltic Gateway - direct and operator channel](https://www.seb.ee/en/business/daily-banking/tools-and-online-services/baltic-gateway)
4. [Coop Pank Gateway - direct and operator channel](https://www.cooppank.ee/en/business/daily-banking/interfaces)
5. [Luminor Web Service - direct channel](https://luminor.ee/business/web-services)

## Direct Channel vs. Operator Channel

Banks | Direct Channel | Operator Channel |
--|--|--
Swedbank Gateway | ✅ | ✅ |
LHV Connect | ✅ | ⏳ | 
SEB Baltic Gateway | ✅ | ✅ |
Coop Pank Gateway | ✅ | ✅ | 
Luminor Web Service | ✅ | ⏳ | 

With the Direct Channel, your ERP software is connected directly to the bank. This solution is available at all banks across the Baltics. A security certificate must be created to allow data transfer. The bank will provide you with instructions for creating the certificate, which is part of the contract signing process. In the [Certificates](#certificates) section, you can have an overview of this step. We recommend having DIGMATIX Estonia handle these tasks.
**NB!** Swedbank also provides instructions for completing setups in the Swedbank Developer Portal. Please follow these steps — your consultant will assist you, if you have any questions.

With the operator channel, DIGMATIX Estonia acts as a data intermediary. This means that your ERP software sends data to us, and we in turn forward it to the bank and vice versa. All connections in the data transfer process are protected by security certificates. In this solution, DIGMATIX Estonia creates and manages all necessary certificates. Bank agreements are generally offered on more favorable terms to users of the operator channel. This solution is at the moment available through Swedbank, SEB, and Coop Pank, and only in Estonia.
**NB!** If you are a user of the Business Central Cloud solution, Coop Pank Gateway is only available to you through the operator channel.

Here you will also find the **link to the Swedbank Gateway operator channel pre-filled application**: https://www.swedbank.ee/business/d2d/ebanking/gateway/conclude?operatorId=47540

## Supported services
### Service descriptions

-  **Transmitting payments to the bank** – pending or unsigned payments.
-  **Regular account statement** or camt.053* – account statement from previous day sent automatically by the bank. 
-  **Urgent notifications** or camt.054* – bank messages automatically sent by the bank for each transaction that meets the set conditions.  
-  **Current day account statement** or camt.053* – replaces the urgent notification feature in certain cases.
-  **LinkPay**** – adds a payment link to invoices and invoice emails.

*Name of service in Luminor, required when signing the contract.  
**Included in our Real-Time Economy package, but from the banks' point of view, it is a completely separate solution. A separate contract is required on the banks' side. Refer to [our LinkPay guide](linkpay.md).

### Supported services by bank


Services | Swedbank | LHV | SEB | Coop Pank | Luminor | 
--|--|--|--|--|--
Transmitting payments to the bank | ✅ | ✅ | ✅ | ✅ | ✅ |
Regular account statement | ✅ | ✅ | ✅ | ✅ | ✅ |
Urgent notifications | ✅ |✅ | | ✅ |✅ |
Current day account statement | ✅ | |✅ | | ✅ |
LinkPay* | ✅ |✅ |✅ | | |


*Refer to [our LinkPay guide](linkpay.md).

### Price list by bank
Coop Pank has created a comparative table of each banks' price lists. It can be found on the Coop Pank Gateway interface page.

Differences in the Direct Channel price list [can be found here](https://www.cooppank.ee/en/business/daily-banking/interfaces#?tab=tab-4&accordionItem=Direct+channel).

Differences in the Operator Channel price list [can be found here](https://www.cooppank.ee/en/business/daily-banking/interfaces#?tab=tab-4&accordionItem=vordlus). **NB!** Operator Channel is supported only through Swedbank, SEB, and Coop Pank Gateway.

## Certificates (direct channel)

A security certificate must be configured in the solution, regarding the bank you join with. The bank will provide you with instructions when you join. As these are quite technical steps, it is advisable to contact your BC partner consultant who will help you to do this.  

In summary, it is necessary to:
- prepare a certificate request to order a certificate;
- join the certificate file and private key file into a pfx/p12 file and generate a password;
- configure both the pfx/p12 file and password in BC.  

### Guides provided by each bank

**Swedbank:**
[http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf](http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf)

[https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html](https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html)

**LHV:**
[https://partners.lhv.ee/en/connect/#certificates](https://partners.lhv.ee/en/connect/#certificates)

**SEB:**
[https://developer.baltics.sebgroup.com/bgw/documentation/authentication](https://developer.baltics.sebgroup.com/bgw/documentation/authentication)

**Coop Pank:**
[Guide in Estonian: https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf](https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf)


## Setup

### Setup Bank Connetors

The following connectors are supported out-of-the-box:
1. Swedbank Gateway
2. SEB Baltic Gateway
3. LHV Connect
4. Coop Pank Gateway
5. Luminor Web Service

Each has its own setup card (e.g., _Swedbank Gateway Setup_). Please open the setup of your bank connector and enter the following information: 

Field |  Description | 
-- | --
Service URL | Enter the address of bank service. <br> Swedbank - https://psd2.api.swedbank.com/partner/v1/sgw/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/ <br> Luminor - https://ftc.luminoropenbanking.com/v1/ft-services/CorporateFileService  
Authorization/Device Certificate Filename | Import certificate file (pfx/p12 format). Certifcate will be given by bank.
Authorization/Device Certificate Password | Enter certificate password.
Agreement Id/Customer Id | Details from the bank agreement.
Service Provider Mode | Turn this on if you have signed an operator channel.

On the same page, using the "Job Queue Entries" function, all job queue entries required for this bank are created. These must be configured according to the desired frequency. 


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

---

### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
