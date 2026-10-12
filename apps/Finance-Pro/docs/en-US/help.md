# Finance Pro
The Finance Pro Solution extends standard financial functionality in Microsoft Dynamics 365 Business Central with the following:
- [Related Dimensions](#related-dimensions)
- [Automatic Default Dimensions](#automatic-default-dimensions)
- [Deferred entries include more information](#deferred-entries-include-more-information)
- [Instant balances of partners](#instant-balances-of-partners)
- [G/L Entries extra info](#gl-entries-extra-info)
- [Instant overview of Fixed Assets](#instant-overview-of-fixed-assets)
- [Fringe benefits](#fringe-benefits-for-estonian-companies)
- [Approval Condition on Purchase Documents](#approval-condition-on-purchase-documents)

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
1. Navigate to page **Dimensions**
2. On the **Global Dimension**, select the **Related Dimensions** action.
   1. _Alternatively, open the Dimension Values for the Global Dimension and select the **Related Dimensions** action there._
3. Add suitable related dimension values to that global dimension value on related dimensions page  

**Setup notes:**
- User cannot select **same** dimension as a related dimension.
- User cannot select a dimension as related, if that dimension **already has** the current dimension set as its related dimension.
- If the user selects a dimension, that is **already defined** as a related dimension for the base dimension, as related, then user is informed about the situation and asked whether they want to continue.
- When the **Base Dimension Value Name** is changed on the **Related Dimensions** page, all corresponding Dimension Value Names for that Dimension Value are updated accordingly.
- When the **Dimension Value Name** is changed on the **Dimension Values** page, the corresponding **Base Dimension Value Name** values are updated accordingly.
- The **Related Dimensions** action is available only when the selected Dimension is configured as **Global Dimension 1** or **Global Dimension 2**.  
<br>

## Automatic Default Dimensions
This feature enables the automatic assignment of Default Dimensions to various master data tables.  
For example, by configuring Automatic Default Dimensions for the Customer table, the Customer No. is automatically assigned as a Default Dimension to each newly created customer. The dimension is then carried through to all entries related to that customer, making reporting easier and more consistent.

Automatic Default Dimensions can be configured for master data tables that support Default Dimensions and have a single unique identifier (a simple primary key), such as:
- Customer
- Vendor
- Employee
- Fixed Asset
- Resource
- Project
- Location
- etc. _(including custom tables that support Default Dimensions)_  

### Setup
To use Automatic Default Dimensions:
1. Create a **Dimension** for the relevant master data table.
   - _This dimension will receive the Dimension Values that are automatically created by the solution._
2. Open the **Automatic Default Dimensions** page and select the appropriate master data table.
3. Select the table field(s) that will be used as the **Dimension Value Name**.
   - _When using multiple fields, separate them with the "&" character._
4. **Link** the master data table to the **Dimension** created in step 1.
5. Select **Synchronize** to create or update the Dimension Values and Default Dimensions for the selected table, including the Dimension Value Name.  

**Setup Notes:**
- Multiple Default Dimensions can be configured for the same table if required, although this is generally not recommended.
  - _For example, the Employee table could be linked to both PERSON and EMPLOYEE dimensions. While this creates duplicate Default Dimensions, such a setup may be justified in specific scenarios._
- The source field(s) for the **Dimension Value Name** are identified automatically whenever possible, but can be changed by the user.  

### Usage
After completing the setup and running **Synchronize**, all existing records in the selected table will have the corresponding Default Dimensions assigned.
When a **new record is created**, the system automatically:
- Creates a new **Dimension Value** in the configured Dimension.
- Assigns that Dimension Value as a **Default Dimension** to the newly created record.  

**Usage Notes:**
- If the user changes the primary key value in the source table (for example, Employee No., Item No., Customer No., etc.), the system automatically updates the corresponding Dimension Value Code.
  - _Note: If the source table is linked to a **Global Dimension**, automatic renaming of the Dimension Value is currently not technically possible. The user is informed accordingly._
- If the user changes the source field(s) used for the **Dimension Value Name**, the system automatically updates the Dimension Value Name as well.  
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

**Notes:**
- If the **FA Posting Date Filter** is added to the Fixed Asset List, the **Book Value** and **Acquisition Cost** will be calculated according to the specified filter.
  - _This makes it easy, for example, to view the fixed asset position as of the end of the previous year directly from the list._
- If there are thousands of fixed assets in list, then opening the list might be slow (_since many of them are calculated aka flowfields_). In that case please hide the fields not needed.  
<br>

## Fringe benefits (for Estonian companies)
This is only activated when Country code in Company information is "EE".  
When activated then on G/L Account card it's possible to mark account as "Fringe Benefit Account" (in section "Fringe Benefits").  
When marked, then it's possible to specify G/L accounts where fringe benefit related taxes are calculated as extra lines on purchase documents.  
<br>

## Approval Condition on Purchase Documents
### Usage
A field **Approval Condition** has been added to the header of purchase documents.  
You can select a value for this field from the **Approval Conditions** table, where you can create your own codes, that can then be used to configure the appropriate approval workflow for the purchase document.  
  
---

For more information please contact DIGMATIX:    
<a href="https://www.digmatix.com/en/contacts" target="_blank">https://www.digmatix.com/en/contacts</a>
