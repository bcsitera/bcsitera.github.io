# Additional Items
Additional Items solution in BC enables following features:

* assign Additional Items for items sold via Sales Orders
* assign Deposit for items which require it


## Settings

You must set up Additional Items for every different combination you use in your sale procsess.

### Additional Items Setup

Before you can manage Customer specific rules it is wise to define general policy for Additional Items and Deposits. You must define the general setup on the
**Additional Items Setup** page. This general setup is typically performed once during the initial implementation. On General FastTab you must select separately how
Additional Items and Deposit are gonna be added on document lines.

|Additional Items Calculation|Explanation|
|---|---| 
| Add After Each Item | Adds Additional Items as new lines after the main product line |
| Document Total At The End | Sums Additional Items at the end of the document lines per item code |

For Deposit calculations you can choose between following options:

|Deposit Calculation|Explanation|
|---|---| 
| Add After Each Item | Adds Deposit as a new line after the main product line |
| Document Total At The End | Sums Deposits at the end of the document lines per deposit code |

If **Add Additional Items at Document Release** and/or **Add Deposit at Document Release** are enabled operations are done automatically on documents.


If all the previous selections are done you have to enable on which documents you want to use the functionality.<br>
**Calculate on Order** - functionality is enabled on Sales Orders <br>
**Calculate on Invoice** - functionality is enabled on Sales Invoices <br>
**Calculate on Credit Memo** - functionality is enabled on Sales Credit Memos <br>


### Settings on Customer Card

In addition for general setup you can specify the customer specific rules on the Customer Card. To do that open the Customer Card and on **Shipping** FastTab you can
choose between following options for Additional Items:

|Additional Items Calculation|Explanation|
|---|---| 
| <blank> | Additional Items calculation is according to general Additional Items Setup page |
| Not Applicable | No Additional Items calculations are done for this customer |
| Add After Each Item | Adds Additional Items as new lines after the main product line |
| Total At The End | Sums Additional Items at the end of the document lines per item code |

And to calculate Deposit:

|Deposit Calculation|Explanation|
|---|---| 
| <blank> | Deposit calculation is according to general Additional Items Setup page |
| Deposit from e-Order | Deposits are imported from the e-document, no additional calculations are done |
| Not Applicable | No Deposit calculations are done for this customer |
| Add After Each Item | Adds Deposit as a new line after the main product line |
| Total At The End | Sums Deposits at the end of the document lines per deposit code |


 ### Additional Item Groups

Additional Items are dependent on the Items you sell. Instead of defining Additional Items to every Customer separately you can create groups. These are called
**Additional Item Groups**. In these groups you define which additional items are always sold together.
Choose search and enter **Additional Item Groups**. To create a new group select **New > give it a Code and Description**. After that select **Actions > Additional
Items**. Additional Items page opens. Fill out the lines with items which are additional to the main item. Description for fields are following: <br>
**Item no** - Additional Item item no<br>
**Quantity (base)** - quantity per base unit <br>
**Type** - type of Additional Item (optional) <br>
**Deposit** - shows if the item acts as a Deposit, taken from Item card field <br>
 
 
### Settings on Item Card

Finally you have to define which Additional Items are connected to main item. For this go to the main Item Card and on FastTab **Additional Items/Deposit** choose
on the field **Additional Items** additional item group what you have defined previously.

If Item Card itself is Deposit, following parameters must be applied: **Type = Non-Inventory** and **Deposit == Yes**.
 
 

### Customer Units of Measure

Sometimes you might have different pallet quantities for different Customers. In order Additional Item Group Quantity (base) to work you must define those differences
in **Customer Units of Measure** page.

|Field|Explanation|
|---|---| 
| Customer No | Customer no to whom exception applies |
| Item No | Item no to which exception applies |
| Unit of Measure Code | Unit of Measure to which exception applies in Item Units of Measure page |

NB! All Units of Measure and Quantities must be set up previously on **Item Units of Measure** page.
 
 
# How to use
 
 
## On sale documents

If all the previous setups are done you are now ready to use functionality. If you enabled option **Add Additional Items/Deposit at Document Release** all Additional
Items will be added automatically when you release the document. But if you want to add them manually here is what you should do. On Sales Order Lines menu click
**Manage > Add Additional Items/Deposit**. In the next window 

|Field|Explanation|
|---|---| 
| Add/Update Additional Items | Adds or updates additional item lines |
| Add/Update Deposit Lines | Adds or updates deposit lines |
| Customer | Choose if selection is to be made according to Sell-To or Bill-To Customer card setup |

---

For more information please contact DIGMATIX:    
<a href="https://www.digmatix.com/en/contacts" target="_blank">https://www.digmatix.com/en/contacts</a>
