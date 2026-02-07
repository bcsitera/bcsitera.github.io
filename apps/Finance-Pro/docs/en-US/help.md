# Finance Pro
The Finance Pro Solution extends standard financial functionality in Microsoft Dynamics 365 Business Central with the following:
- [Related Dimensions](#related-dimensions)
- [Deferred entries include more information](#deferred-entries-include-more-information)
- [Instant balances of partners](#instant-balances-of-partners)
- [G/L Entries extra info](#gl-entries-extra-info)
- [Instant overview of Fixed Assets](#instant-overview-of-fixed-assets)
- [Fringe benefits](#fringe-benefits-for-estonian-companies)
- [Approval Condition on Purchase Documents](#approvalcondition-onpurchase-documents)

<br>

# Functionality
## Related Dimensions
This functionality makes possible to connect other dimension values to a global dimension value (_so it's possible to create a so called dimension tree_).
After setup is done and user selects global dimension value (_that has connected dimensions_) to entry, then automatically all related dimensions shall also be added.

This is possible on the following entities:
- Sales header and lines (incl. sales order, sales invoice and sales credit memo)
- Purchase header and lines (incl. purchase order, purchase invoice and purchase credit memo)
- General Journal
- Fixed Asset G/L Journal and Fixed Asset Journal
- Payment Journal and Payment Reconciliation Journal
- Item Journal

### Setup
To use related dimensions it's needed to connect related dimension values to a global dimension value:
1. Navigate to dimensions
2. Open dimension values for a global dimension
3. Select action "Related Dimensions"
4. Add suitable related dimension values to that global dimension value on related dimensions page  

**Setup notes:**
- User cannot select same dimension as a related dimension.
- User cannot select a dimension as related, if that dimension already has the current dimension set as its related dimension.
- If the user selects a dimension, that is already defined as a related dimension for the base dimension, as related, then user is informed about the situation and asked whether they want to continue.  
<br>

## Deferred entries include more information
This functionality adds line description to the deferral schedule lines description and from there it goes to general ledger entries.
- Deferred entries can now include description from related:
  - Sales line
  - Purchase line
  - Journal line

  Note! On Sales/Purchase documents only description from line type "G/L Account" is added to to deferral schedule lines description, because these are not combined (merged) during posting (_unlike for example lines with type Item_).  

### Setup
To use line descriptions from sales/purchase documents navigate to "Sales & Receivables Setup" and/or "Purchases & Payables Setup" and enable: 
- "Copy Line Descr. to G/L Entry" (_this makes below field visible_)
- "Add Line Description to Deferral Entries"

Note! When using general journals, then no setup is needed (_meaning journal line description is always added to deferral schedule lines description_).  
<br>

## Instant balances of partners
This functionality makes possible to get balance at any date quickly by only using date filter in Customer/Vendor list.
Add date filter and new field "Balance (LCY) at Date" shows balance on the last date included in the Date Filter field.  
<br>

## G/L Entries extra info
Following information is added to general ledger entries:
- Source Name and Balance Account Name
  - Depending of source type this may be
    - Customer name
    - Vendor name
    - Employee name
    - Fixed Asset name
    - Bank Account name  
<br>

## Instant overview of Fixed Assets
- Added fields to Fixed Asset list:
  - Book Value
  - Acquisition Cost
  - Acquisition Date
  - Depreciation %
  - Depreciation Book Code
  - Depreciation Starting Date
  - Depreciation Ending Date
  - No. of Depreciation Years
  - Remaining Depreciation Time
  - Disposal Date
  - Next Service Date
  - Warranty Date
  - Serial No.
  - Vendor Name
  - Maintenance Vendor Name   

Note! If there are thousands of fixed assets in list, then opening the list might be slow (_since many of them are calculated aka flowfields_). In that case please hide the fields not needed.  
<br>

## Fringe benefits (for Estonian companies)
This is only activated when Country code in Company information is "EE".  
When activated then on G/L Account card it's possible to mark account as "Fringe Benefit Account" (in section "Fringe Benefits").  
When marked, then it's possible to specify G/L accounts where fringe benefit related taxes are calculated as extra lines on purchase documents.  
<br>

## Approval Condition on Purchase Documents
### Usage
A field "Approval Condition" has been added to the header of purchase documents.  
You can select a value for this field from the "Approval Conditions" table, where you can create your own codes, that can then be used to configure the appropriate approval workflow for the purchase document.  
  
---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
