
---
---
# LinkPay - User Guide
## Table of Contents

- [Setup](#setup)
- [User Guide](#user-guide)

## Setup

### Bank Agreement

LinkPay functionality is currently offered by three banks:
1. **[LHV](https://www.lhv.ee/en/payment-acquiring)**
2. **[SEB](https://www.seb.ee/en/business/payment-collection/e-commerce)**
3. **[Swedbank](https://www.swedbank.ee/business/d2d/start)**

To start accepting online payments, you must contact the appropriate bank. Choose the bank in which your accounts are located. The pricing is agreed upon the bank agreement.

The provider's guide to using the EveryPay Merchant Portal can be found [here](https://support.every-pay.com/merchant-support/linkpay-payment-link/).
Pay attention to step no. 2, which includes a reference to an even more detailed guide to [creating and managing payments links](https://support.every-pay.com/merchant-support/how-to-use-linkpay/).

### LinkPay Setup
#### General


Field |  Description | 
-- | --
LinkPay Prefix | Open _EveryPay Merchant Portal_, section _Links_ - each link has a URL and a _Link Token_. **_Prefix_ is the URL without the _Link Token_**.
API Username | From _EveryPay Merchant Portal_, section _General Settings_.
API Secret | From _EveryPay Merchant Portal_, section _General Settings_.
Link Token | Open _EveryPay Merchant Portal_, section _Links_ - each link has a URL and a **_Link Token_**.
LinkPay Text | Text displayed as the payment link.
LinkPay Picture | Image displayed as the payment link.


#### Link Parameters


Field |  Description |
--|--
Link Field Name | The fields chosen when creating a payment link in _EveryPay Merchant Portal_.
BC Field Name  | The corresponding fields in Business Central based on Sales Header.



## User Guide
In order to use LinkPay, you will also need to create a report layout for email and invoice designs. 

To do this, you will need to contact your consultant in order for the developer to create the report layouts in Business Central.

---
### Contact Information
For more information and pricing please contact:  
[https://apps.itera.ee/docs/en-us/support](https://apps.itera.ee/docs/en-us/support)