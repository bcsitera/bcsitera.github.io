
# Joining

## Submitting the application

Our Business Central product uses a direct channel for interfacing. To join, contact your customer manager or submit an application on the bank's website.

Võimalik on seadistada pangaühendused järgmiste pankadega:

1. [Swedbank Gateway](https://www.swedbank.ee/business/d2d/ebanking/gateway)

2. [LHV Connect](https://www.lhv.ee/en/connect)

3. [SEB Baltic Gateway](https://www.seb.ee/en/business/daily-banking/tools-and-online-services/baltic-gateway)

4. [Coop Pank Gateway](https://www.cooppank.ee/en/business/daily-banking/interfaces)

5. [Luminor Web Service](https://luminor.ee/business/web-services)

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


Teenused | Swedbank | LHV | SEB | Coop Pank | Luminor | 
--|--|--|--|--|--
Transmitting payments to the bank | ✅ | ✅ | ✅ | ✅ | ✅ |
Regular account statement | ✅ | ✅ | ✅ | ✅ | ✅ |
Urgent notifications | ✅ |✅ | | ✅ |✅ |
Current day account statement | ✅ | |✅ | | ✅ |
LinkPay* | ✅ |✅ |✅ | | |


*Refer to [our LinkPay guide](linkpay.md).

### Price list by bank
Coop Pank has created a comparative table of each banks' price lists. It can be found [here](https://www.cooppank.ee/en/business/daily-banking/interfaces#?tab=tab-3&accordionItem=Direct+channel).

## Certificates

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
[https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf](https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf)

---

### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)
