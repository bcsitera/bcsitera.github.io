# HRM4Baltics connection to Object Management and Billing Solution
This extension provides HRM4Baltics connection to Object Management and Billing Solution for Microsoft Dynamics 365 Business Central.  

## Solution makes possible:
#### Use HRM4Baltics employees in Objects
#### Use objects on HRM4Baltics tables
#### Create G/L Budget for Working Schedule

<br>  

## Settings
To use the solution, **Object Management Setup** must be opened and following fields filled:

|Field|Explanation|
|---|---| 
| Working Schedule Budget Hours Account | Specifies accounts for Working Schedule Budget **Hours**.|
| Working Schedule Budget Amount Account | Specifies accounts for Working Schedule Budget **Amount**.|
| Working Schedule Budget Posting Journal Template | Specifies Budget Posting Journal **Template** for Working Schedule.|
| Working Schedule Budget Posting Journal Batch | Specifies Budget Posting Journal **Batch** for Working Schedule.|
| Working Schedule Budget Posting Doc No. Prefix | Specifies the document number **prefix** for posting Working Schedule Budget Amounts.|  

NB! Please select to **Employee Source** field **HRM4Baltics Employee**, because then user can select employees from Employee (HRM4Baltics) table.  

<br>  

## Use
### HRM4Baltics employees in Objects
If setup is done correctly then user selects Employee from Employee (HRM4Baltics) table.
No extra steps/logic is needed.  

### Objects on HRM4Baltics tables
User can now fill object field on HRM4Baltics tables:
- Employee (HRM4Baltics)
- Employee Salaries
- Expense Report Line
- Payroll Journal
- Payroll Accounts
- Working Schedule Groups 

Filling object number activates functionality that handles automatically default dimensions from objects.  

## Create G/L Budget for Working Schedule
If setup is done correctly then user can use G/L budget to create Budget for Working Schedule.  

---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
