# Object Management
The Object Management Solution in Business Central enables the following: 
- Manage objects
- Manage services and items used on object
- Handle billing

## Settings
To use the solution, **Object Management Setup** must be opened and following fields filled:

|Field|Explanation|
|---|---| 
| Object Nos. | To specify number series for Objects. Value can be chosen from **No. Series List**.|
| Object Contract Nos. | To specify number series for Object Contracts. Value can be chosen from **No. Series List**.|
| Object Finance Report | Specifies the finance report that is used to view object''s Budjet vs Actual information from action on object card.|
| Object Budget Finance Report | Specifies which financial report is used to generate the Print Budget report on object budget page.|
| Employee Source | Specifies the source table of employees.|
| Price Calculation Method | Specifies the price calculation method for objects and sales invoices. It''s rec commended to use Object price in order to show correct prices on object.|  

<br>
In Dimension section:

|Field|Explanation|
|---|---| 
| Object Dimension Code | Specifies the dimension code used for objects. System also uses this to automatically create default dimension to object.|
| Budget Second Dimension Code | Specifies the value of the Second dimension filter opening Budget from Object Card. (Global dimension 1 is supposed to be Object dimension).|
| Dimension Update Filter | Specify dimensions that are updated on entries (G/L, FA, Budget, Analysis View entries), if they change on object. To add many dimensions use vertical bar (e.g. OBJECT&#124;MANAGER).|
| Item Default Dimension | Specify dimension used for items, so that system can automatically create a corresponding new dimension value, when a new item is created.|
| Item Category Default Dimension | Specify dimension used for item categories, so that system can automatically create a corresponding new dimension value, when a new item category is created. When item category is selected to an item, then a corresponding default dimension value will be added to Item.|  

It's also possible to specify 8 Object Attributes, that are displayed on **Objects and attributes** page as columns.

Action **Person Role Default Dimensions** is used to specify dimensions to person roles, so that they are automatically used with that role.

## Use
### Objects
Object table is the central part of the solution.  
There user can enter various data and information in the following sections:
* Object information (name, type, connected assets etc)
  * Specify Purchase line approval template, if needed to approve purchase lines connected to objects
* Object notes (text, table or graphics that describe the object)
* Aaddress info (for most accurate position a geolocation position can be entered)
* Connected persons (own employees, customer contacts, third party contacts etc)
* Billing related info (object global dimensions etc)
* Object sales lines (recurring monthly billable services on that object)
  * Price can be entered through field Current price
  * Diferent lines can have different contracts
  * Services can be seasonal
* Items/Implements (items agreed to be used on object along with the billable services)
  * Specify there whether items are included in service price or should be sold separately as resale item.

### Object Contracts
Object contract is needed for financial specification when creating invoices.  
_It's not mandatory to have a contract related to object line, but it's highly recommended._  
User can select to have all objects for one contract to be on single invoice or to create one invoice for every object.  



### Billing
To create montly recurring billing user can use action "Create Object Invoices".
Solution creates invoices for all objects that have valid object sales lines.  

---

For more information please contact BCS Itera AS:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">www.itera.ee/en/about-us/</a>
