# User manual

## Solution offers:
- Automatic change of Customer/Vendor posting group when posting prepayment invoices
- Change of Customer posting group on sales invoice/order
- Change of Vendor posting group on purchase invoice/order 

## Setup
### Prepayment invoice automatic Customer/Vendor posting group change
On Customer/Vendor Posting Groups page, there's a field **Prepayment Invoice Customer/Vendor Posting Group**.  

There User can specify an alternative Customer/Vendor posting group, that shall be used when posting Prepayment invoices from Sales/Purchase order.  

Attention! If prepayment invoices are not used, then setup of alternative Customer/Vendor posting group is not needed.  

### Job queues
During installation of solution two job queues are automatically created in order to correct Business Central's standard logic general ledger entries when invoices are applied/unapplied (done according to Customer/Vendor posing group specified on Customer/Vendor card).  

**Job que codeunit is 24013200** and parameters are:  
-"**CUSTOMER**" (to correct Customer receivables account on application/unapplication of Customer payments/application/unapplication)  
-"**VENDOR**" (to correct Vendor payables account on application/unapplication of Vendor payments/application/unapplication)    

By default the No. of minutes between runs is 15. User can change this to any suitable value.

<br>
On Job que's firs run system checks detailed customer/vendor ledger entries from previous 3 months in order to find correction needing entries. Last checked entry no is then saved on Sales & Receivables / Purchase & Payables setutp accordingly.  


## Use
### Prepayment invoice
When posting prepayment invoice from Sales/Purchase order **solution automatically uses Prepayment Invoice Customer/Vendor Posting Group** specified on Customer/Vendor Posting Group's page.


### Manual change of Customer/Vendor Posting Group on Sales/Purchase invoice and order 
On Sales- and Purchase invoice/order header **'User can change** Customer/Vendor posting group. Likewise this change can be done on Sales- and Purchase credit memo header.  
<br>
Note! On Sales/Purchase Order header the field Customer/Vendor posting group can be made visible via Personalization.

---

For more information please contact DIGMATIX:    
<a href="https://www.digmatix.com/en/contacts" target="_blank">https://www.digmatix.com/en/contacts</a>
