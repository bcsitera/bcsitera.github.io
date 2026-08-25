# Public Sector Accounting and Reporting
Public Sector Accounting and Reporting solution in Business Central enables the following:

- Management of State G/L Accounts
- Management of State Transaction Partners
- Management of State Balance Reports
 - Submit State Balance Report as XML file to Estonian State Balance Reports Information System
- Management of State Payment Reports
 - Submit State Payment Report as XML file to Estonian State Balance Reports Information System
<br><br>

## Settings
### Dimensions
Solution uses dimension values from G/L entries when creating State Balance Report, so separate dimensions for  the following information is needed:
 - Transaction Partner
 - Business Activity
 - Source
 - Cashflow
 <br><br>

### State Finance Setup
In **section Dimensions** we specify dimensions necessary for solution:

|Field|Explanation|
|---|---| 
| Transaction Partner Dimension Code | Dimension code for the dimension that is used for **Transaction Partners**.|
| Business Activity Dimension Code | Dimension code for the dimension that is used for **Business Activity**.|
| Source Dimension Code | Dimension code for the dimension that is used for **Source**.|
| Cashflow Dimension Code | Dimension code for the dimension that is used for **Cashflow**.|
| Conditional Cashflow Dimension Value | Specific dimension value from Cashflow dimension values. Used for conditional logic when creating State Balance Report lines. Usually value is **01**.|

For more information on possible dimension values please visit <a href="https://saldo.rtk.ee/saldo-app/" target="_blank">State Balance Reports Information System</a>
<br><br>

In **section General** we specify :

|Field|Explanation|
|---|---| 
| State Balance Report No. Series | Specifies **State Balance Report** number series. Value can be chosen from **No. Series List**.|
| Transaction Partner No. Series | Specifies **Transaction partner** number series. Value can be chosen from **No. Series List**.|
| Company Transaction Partner Code | Specifies **company's own Transaction partner code** used in State Balance Report XML file.|
| Company Business Activity Code | Specifies **company's main Business activity code**. Dimension value here shall be automatically added as Default dimension value, when applying State accounts to G/L Accounts.|
| State Payment Report No. Series | Specifies the code for the number series that will be used to assign numbers to **State Payment Reports**.|
| Exclude Transaction Partner from Payment Report | Specifies transaction partner dimension values **to be excluded** from State payment report. (For example 014001 and 800699).|
| Report Payments from Amount | Specifies the bank account entry''s **starting amount** that''s reported in State Payment Report (usually 100).|


### State G/L Accounts
Solution shall fill State Accounts table with default values on first install.<br>
State G/L Accounts table consists of accounts that have number, name and settings about mandatory dimensions for that account.<br>
Transaction Partner and/or Business Activity can be **conditionally mandatory**, meaning corresponding dimension is mandatory only when transaction''s Cashflow dimension has specific predetermined value (usually 01).

Configure following fields for better user experience and more accurate State Balance Report:

|Field|Explanation|
|---|---| 
| Constant TP Dimension | Specifies constant transaction partner dimension value for State G/L Account. **Value here shall override any Transaction Partner dimension value on General Ledger Entries**. Typically used for tax accounts, because there can be only one transaction partner code for Tax and Customs Board.<br> ***Note!** If value is specified here, then there is no need for Code Mandatory setting for Transaction Partner dimension in corresponding G/L Account's default dimensions.*|
| Use Constant TP Dimension on Bank Account | Specifies if system uses **Constant State Transaction Partner dimension value specified on Bank Account card to override any Transaction Partner value on General Ledger Entries**. Typically used for cash accounts.<br> ***Note!** When using Constant State Transaction Partner dimension value on Bank Account card, a Default dimension for Bank Account Card should NOT be used.*|
| State Account Class Exception | Specify manually a **value for state account class**. If not specified then state account''s first two digits are used as state account''s class.|
| Blocked | Specifies that the state account **is not selectable** to G/L Account, State Balance report and State Payment report.|


User can reset state accounts table to default values with button "**Reset State G/L Accounts**".
**Warning!** this shall delete all user configurations in State Accounts and restore the default values.
<br><br>

### Chart of Accounts
Specify for each G/L Account a corresponding State Account No. *This field can be found on G/L Account card and on Chart of Accounts.*<br>
When State Account No. is entered, solution shall check the mandatory dimensions for that account in State G/L Accounts. **If a dimension is mandatory or conditionally mandatory then solution will add Code Mandatory value posting condition to Default Dimensions** for that G/L Account.<br>
***Note!** If for certain G/L Account User determines that no transaction with Cashflow conditional dimension shall ever be posted there, User should manually remove Code Mandatory value posting condition from Default Dimensions concerning  Transaction Partner and/or Business Activity dimension.*
<br><br>

### State Transaction Partners
For initial setup User should create Transaction Partners.<br>
User can **download Transaction Partners XML file** from Balance Reports Information System with button "Download fresh Partners XML".<br>
User can **import/update** **Transaction Partners** from XML file with button "Import Partners From XML".<br>
***Note!** Since there are no unique identifiers in state created XML file, then record shall be updated only if same combination of Code + Name + Valid from date exists. Otherwise a new record will be created.*
<br><br>

### Customers/Vendors
For every Customer/Vendor User should **specify a corresponding Transaction Partner**. This can be done **on Customer/Vendor card** in section State Accounting information.<br>
When Transaction Partner Id is selected, solution adds corresponding Transaction Partner code to Transaction Partner dimension values and also a default dimension with that dimension value code along with value posting condition Same Code is added to Customer/Vendor.
<br><br>

### Bank Accounts
For every bank's cash account User should **specify a Constant State TP Dimension**. This can be done on Bank Account Card.<br>
This specifies constant transaction partner dimension for current bank account's bank and therefore **there is no need for Default dimension value**.<br>
This dimension value will be used in State Balance Report, if field "Use Constant Bank Account TP Code" is selected in table State G/L Accounts.<br>
***Note!** When using Constant State Transaction Partner dimension value on Bank Account card, a Default dimension Code Mandatory value posting condition for corresponding G/L Account (look via Bank Acc. Posting Group) should be removed.*<br>
**Include in State Payment Report** - Specifies whether the bank account''s entries are included in State Payment report.
<br><br>


## Use
### General Ledger Entries
Mandatory dimensions specified in chart of accounts default dimensions must be added to every transaction concerning General Ledger. Also a corresponding State G/L Account No. is saved to G/L entries. With this information solution is able to create State Balance Reports.
<br><br>

### State Balance Reports
To create a new Balance Report User must specify Year and Month of the reporting period. State balance report is a cumulative report from the beginning of reporting period's calendar year.<br>
Button **"Calculate Lines" creates State Balance Report Lines**. *Lines are created for every State G/L Account in combination with Transaction Partner, Business Activity, Source and Cashflow.*

In order to check General Ledger Entries that form a State Balance Report Line, look for button "**Show entries**" in State Balance Report Lines. To view entries with all dimensions in General Ledger Entries navigate to Entry and press button G/L Dimension Overview and then Show Matrix.
<br><br>
If there are incorrect values found on some State Balance Report Lines, due to incorrect dimensions used on General Ledger entries, then use <a href="http://apps.itera.ee/apps/dimension-correction-tool/docs/en-US/app.html" target="_blank">Dimension Correction Tool</a> to fix those entries.
After a correction in entries, User must Calculate Lines to view the corrected result in State Balance Report Lines.
<br><br>
Button "**Create XML File**" saves created State Balance Report to XML file that can be imported to Estonian State Balance Reports Information System.  


### State Payment Reports
To create a new Payment Report User must specify Year and Month of the reporting period.<br>
Button **"Calculate Lines" creates State Payment Report Lines**.  
Lines are created for every bank payment over the amount specified in State Finance Setup and for all bank accounts that are specified as "Include in State Payment Report".  
Note! In General Ledger Entries it's possible to use action **Exclude entry from State Payment Report** to exclude entry (_for example entry with state secrecy_) from State Payment Report.
<br><br>
System finds every purchase invoice related to payment and looks through every line to find expense classes. In case payment was partial, then system calculates amounts poprtionally.  
In case payment is not related to any invoice and only to G/L account then system finds Transaction partner and State account no from that general ledger entry and so determines expense class.
<br><br>
Button "**Create XML File**" saves created State Balance Report to XML file that can be imported to Estonian State Balance Reports Information System.

---

For more information please contact DIGMATIX:    
<a href="https://www.digmatix.com/en/contacts" target="_blank">https://www.digmatix.com/en/contacts</a>
