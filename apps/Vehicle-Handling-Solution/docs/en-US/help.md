# Vehicle Handling
The Vehicle Handling Solution in Business Central enables the following: 
- Manage vehicles
- Manage data related to vehicle
- Manage mileage log
- Get overview of vehicle costs

## Settings
To use the full functionality the **Vehicle Handling Solution Setup** should be opened and following fields filled:

|Field|Explanation|
|---|---| 
| Vehicle Dimension Code | Specifies the dimension code used for vehicles. When adding a new vehicle, the corresponding **dimension value is automatically created**. Using vehicle''s dimension value on a purchase invoice line as shortcut dimension, the global dimensions related to the vehicle are **automatically** added, along with the VAT product posting group (_if the vehicle categories have the corresponding setting_).|
| Employee Source | Specifies the source table of employees.|
| Vehicle Checking Service URL | Specifies the **URL for the vehicle checking service**. You can use parameters in the URL, marking them as %1, %2 (_depending of selection in "Field as Service Parameter"_).<br>For example enter URL "https://www.autodna.com/vin/%1" and select "VIN Code" as service parameter.|
| Field as Service Parameter | Specifies the field used as a **parameter** in the vehicle checking service URL (_when both selected then use %1 and %2 in URL, otherwise just %1_).|  

<br>
In Vehicle summarized cost overview section:

|Field|Explanation|
|---|---| 
| Vehicle Fuel Accounts Filter | Specifies **fuel** expense G/L **accounts**. The defined accounts filter is used in the calculation of the vehicle summarized fuel cost for the previous period. Multiple G/L accounts can be added, for example 8510\|8511.|
| Vehicle Fuel Unit of Measures Filter | Specifies the **unit of measure** used for **fuel** quantity on purchase invoices. Multiple unit of measures can be added, for example L\|PCS\|''.|
| Vehicle Summary Start Date Formula | Specifies the **start of period formula** for showing vehicle summarized costs. For example, the beginning of last month is: -CM-1M, the beginning of last quarter is: -CQ-1Q-CM and the beginning of last year is: -CY-1Y.|
| Vehicle Summary End Date Formula | Specifies the **end of period formula** for showing vehicle summarized costs. For example, the formula for the end of last month is: +CM-1D, for end of last quarter is: +CQ-1Q+CM and for the end of last year is: +CY-1D.|  

<br>
  
**Setup Vehicle Data Types**  
It's possible to specify up to 15 **Vehicle Data Types**, that are displayed on **Vehicle register**.
For example, you can add category, responsible user, leasing provider, fuel and wash card, insurance, etc. data to a vehicle.  

To setup Vehicle Categories, select **Vehicle Category** as table relation in Vehicle Data Types page. Use action **Setup Vehicle Categories** to setup selectable categories. The Category can be linked to the VAT Product Posting Group, which is used to calculate VAT on the purchase invoice line related to the vehicle.  

<br>

## Use
### Vehicle Register
Vehicle Register is the central part of the solution.  
There user can enter various data and information in the following sections:
* Vehicle info (License plate (_Number plate_), VIN code, Category, Engine power, etc)
* Inspection details
* View vehicle background history
* Manage (enter) data related to vehicle:
  * Responsible employee
  * Fuel and wash cards
  * Lease, maintenance, insurance vendor and validity periods
  * etc.
* Manage vehicle mileage log
  * Import mileage log from Excel or create it manually

### Technical Inspection reminders
System can send **via email** a technical inspection reminders to the fleet manager or responsible employee, if the inspection date has passed or falls within the period specified by the inspection reminder period date formula.  
The reminders are sent using Notification email scenario _(and therefore from the email account related to that scenario)_.  
System can send technical inspection reminders **automatically**, if a job for Codeunit 70467425 _(BCS.VHS Vehicle Reminders)_ is configured in Job Queue Entries.  

### Overview of period costs
In **factbox** on vehicle register card and list is **Last Period Summary**, where system shows:
* Total Mileage
* Total Fuel in Units
* Total Fuel Cost
* Fuel Cost Per Mileage Unit
* Total Cost
* Total Cost Per Mileage Unit

Costs are retrieved from **Purchase invoice lines** using Vehicle dimension.  

---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
